---
title: Перенос исключений между потоками | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- std::current_exception
- transporting exceptions between threads
- std::copy_exception
- exception_ptr
- std::exception_ptr
- std::rethrow_exception
- current_exception
- transport exceptions between threads
- copy_exception
- rethrow_exception
- move exceptions between threads
ms.assetid: 5c95d57b-acf5-491f-8122-57c5df0edd98
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1066da6545a2e0689fbfed33be466e001142dc9
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704650"
---
# <a name="transporting-exceptions-between-threads"></a>Перенос исключений между потоками

Visual C++ поддерживает *передачу исключения* из одного потока в другой. Передача исключений позволяет перехватывать исключение в одном потоке и затем обеспечить видимость того, что исключение возникло в другом потоке. Например, эту возможность можно использовать для создания многопоточного приложения, где первостепенный поток обрабатывает все исключения, создаваемые его второстепенными потоками. Передача исключений в основном полезна для разработчиков, создающих системы или библиотеки параллельного программирования. Для реализации передачи исключений Visual C++ предоставляет [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) типа и [current_exception](../standard-library/exception-functions.md#current_exception), [rethrow_exception](../standard-library/exception-functions.md#rethrow_exception), и [make_ exception_ptr](../standard-library/exception-functions.md#make_exception_ptr) функции.

## <a name="syntax"></a>Синтаксис

```cpp
namespace std
{
   typedef unspecified exception_ptr;
   exception_ptr current_exception();
   void rethrow_exception(exception_ptr p);
   template<class E>
       exception_ptr make_exception_ptr(E e) noexcept;
}
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*Не указан*|Неуказанный внутренний класс, используемый для реализации типа `exception_ptr`.|
|*p*|Объект `exception_ptr`, который ссылается на исключение.|
|*E*|Класс, представляющий исключение.|
|*e*|Экземпляр класса `E` параметров.|

## <a name="return-value"></a>Возвращаемое значение

Функция `current_exception` возвращает объект `exception_ptr`, который ссылается на исключение, выполняемое в данный момент. Если никакое исключение не выполняется, функция возвращает объект `exception_ptr`, не связанный ни с одним исключением.

`make_exception_ptr` Возврата функцией `exception_ptr` объект, который ссылается на исключение, заданное параметром *e* параметра.

## <a name="remarks"></a>Примечания

### <a name="scenario"></a>Сценарий

Предположим, что требуется создать приложение, которое может масштабироваться для выполнения переменного объема работы. Для достижения этой цели создается многопоточное приложение, где исходный основной поток создает столько второстепенных потоков, сколько необходимо для выполнения задачи. Второстепенные потоки помогают первичному потоку распоряжаться ресурсами, распределять нагрузку и повышать пропускную способность. Благодаря распределению работы многопоточное приложение работает быстрее, чем однопоточное.

Однако если второстепенный поток вызывает исключение, необходимо обеспечить его обработку основным потоком. Это обусловлено тем, что требуется обеспечить обработку исключений приложением единообразным, унифицированным способом независимо от количества второстепенных потоков.

### <a name="solution"></a>Решение

Для выполнения указанного выше сценария стандарт C++ поддерживает передачу исключений между потоками. Если второстепенный поток вызывает исключение, это исключение становится *текущее исключение*. Используя аналогию из реального мира, текущее исключение считается *в полете*. Текущее исключение находится в полете со времени создания до возвращения результата обработчиком исключений, перехватывающим его.

Второстепенный поток может перехватить текущее исключение в блоке `catch`, а затем вызвать функцию `current_exception` для сохранения исключения в объект `exception_ptr`. Объект `exception_ptr` должен быть доступным для второстепенного и первичного потоков. Например, объект `exception_ptr` может быть глобальной переменной, доступ к который регулируется мьютексом. Термин *передавать исключение* означает исключение в одном потоке можно преобразовать в форму, доступный другим потоком.

Далее основной поток вызывает функцию `rethrow_exception`, которая извлекает исключение из объекта `exception_ptr` и затем вызывает его. При вызове исключения оно становится текущим исключением в основном потоке. Это означает, что создается видимость того, что исключение возникает в основном потоке.

Наконец, основной поток может перехватить текущее исключение в блоке `catch` и затем обработать его или передать его обработчику исключений верхнего уровня. Также основной поток может проигнорировать исключение и позволить процессу завершиться.

Большинству приложений не требуется передавать исключения между потоками. Однако эта функция полезна в системе параллельных вычислений, поскольку система может распределить работу между второстепенными потоками, процессорами или ядрами. В среде параллельных вычислений один выделенный поток может обрабатывать все исключения из второстепенных потоков и может предоставлять единообразную модель обработки исключений любому приложению.

Дополнительные сведения о предложении Комитета по стандартам C++ можно получить, найдя в Интернете документ с номером N2179 «Поддержка передачи исключений между потоками в языке».

### <a name="exception-handling-models-and-compiler-options"></a>Модели обработки исключений и параметры компилятора

Модель обработки исключений приложения определяет, возможен ли в нем перехват и передача исключения. Visual C++ поддерживает 3 модели, которые могут обрабатывать исключения C++, исключения структурированной обработки (SEH) и исключения среды CLR. Используйте [/EH](../build/reference/eh-exception-handling-model.md) и [/CLR](../build/reference/clr-common-language-runtime-compilation.md) параметры компилятора для указания модель обработки исключений приложения.

Только следующее сочетание параметров компилятора и операторов программирования может передавать исключение. Другие сочетания либо не могут перехватывать исключения, либо могут перехватывать, но не могут передавать исключения.

- **/EHa** параметр компилятора и `catch` инструкции могут передавать исключения SEH и C++.

- **/EHa**, **/EHs**, и **/EHsc** параметры компилятора и `catch` инструкции могут передавать исключения C++.

- **/CLR** параметр компилятора и `catch` инструкции могут передавать исключения C++. **/CLR** параметр компилятора подразумевает спецификацию **/EHa** параметр. Обратите внимание, что компилятор не поддерживает передачу управляемых исключений. Это, поскольку управляемые исключения, которые являются производными от [класса System.Exception](../standard-library/exception-class.md), уже являются объектами, которые можно перемещать между потоками с помощью средства languange среды выполнения.

   > [!IMPORTANT]
   > Мы рекомендуем указывать **/EHsc** параметр компилятора и перехватывать только исключения C++. Предоставить себе угрозу безопасности, при использовании **/EHa** или **/CLR** параметр компилятора и **перехватывать** инструкции с многоточием  *объявления исключения* (`catch(...)`). Возможно, планируется использовать оператор `catch` для перехвата нескольких конкретных исключений. Однако оператор `catch(...)` перехватывает все исключения C++ и SEH, включая непредвиденные, которые должны приводить к сбою. Если непредвиденное исключение игнорируется или обрабатывается неверно, вредоносный код может использовать эту возможность, чтобы подорвать безопасность программы.

## <a name="usage"></a>Использование

В следующих разделах описаны способы передачи исключений с помощью `exception_ptr` типа и `current_exception`, `rethrow_exception`, и `make_exception_ptr` функции.

## <a name="exceptionptr-type"></a>Тип exception_ptr

Используйте объект `exception_ptr` для ссылки на текущее исключение или экземпляр указанного пользователем исключения. В реализации Майкрософт исключение представлено структурой [EXCEPTION_RECORD](https://msdn.microsoft.com/library/windows/desktop/aa363082). Каждый объект `exception_ptr` содержит поле ссылки на исключение, указывающее на копию структуры `EXCEPTION_RECORD`, представляющую исключение.

При объявлении переменной `exception_ptr` эта переменная не связана ни с одним исключением. То есть в поле ссылки на исключение находится значение NULL. Такой объект `exception_ptr` называется *exception_ptr null*.

Используйте функцию `current_exception` или `make_exception_ptr` для назначения исключения объекту `exception_ptr`. При назначении исключения переменной `exception_ptr` поле ссылки на исключение переменной указывает на копию исключения. При нехватке памяти для копирования исключения поле ссылки на исключение указывает на копию исключения [std::bad_alloc](../standard-library/bad-alloc-class.md). Если `current_exception` или `make_exception_ptr` функции не удается скопировать исключение по другой причине, эта функция вызывает [завершить](../c-runtime-library/reference/terminate-crt.md) функции, чтобы выйти из текущего процесса.

Несмотря на свое имя, объект `exception_ptr` не является указателем. Он не повинуется семантике указателя и не может использоваться с доступа к членам указателей (`->`) или косвенного обращения (`*`) операторы. Объект `exception_ptr` не имеет открытых данных-членов и функций-членов.

### <a name="comparisons"></a>Сравнения

Можно использовать операторы равенства (`==`) и неравенства (`!=`) для сравнения двух объектов `exception_ptr`. Эти операторы не сравнивают бинарное значение (битовый шаблон) структур `EXCEPTION_RECORD`, которые представляют исключения. Вместо этого операторы сравнивают адреса в поле ссылки на исключение объектов `exception_ptr`. Поэтому `exception_ptr` со значением null и значение NULL при сравнении считаются равными.

## <a name="currentexception-function"></a>Функция current_exception

Вызовите функцию `current_exception` в блоке `catch`. Если исключение находится в полете и блок `catch` может перехватить это исключение, функция `current_exception` возвращает объект `exception_ptr`, который ссылается на это исключение. В противном случае функция возвращает объект `exception_ptr` со значением null.

### <a name="details"></a>Подробные сведения

Функция `current_exception` перехватывает исключение, находящееся в полете, независимо от того, определяет ли `catch` оператор [объявления исключения](../cpp/try-throw-and-catch-statements-cpp.md).

Деструктор для текущего исключения вызывается в конце блока `catch`, если не требуется повторно создавать исключение. Но даже при вызове функции `current_exception` в деструкторе эта функция возвращает объект `exception_ptr`, который ссылается на текущее исключение.

Последующие вызовы функции `current_exception` возвращают объекты `exception_ptr`, которые ссылаются на различные копии текущего исключения. Соответственно, при сравнении объекты не признаются равными, поскольку они ссылаются на различные копии, даже если эти копии имеют одинаковые бинарные значения.

### <a name="seh-exceptions"></a>Исключения SEH

Если вы используете **/EHa** параметра компилятора можно перехватить исключение SEH в C++ `catch` блока. Функция `current_exception` возвращает объект `exception_ptr`, который ссылается на исключение SEH. И `rethrow_exception` функция вызывает исключение SEH, если она вызывается с thetransported `exception_ptr` объект в качестве своего аргумента.

Функция `current_exception` возвращает значение `exception_ptr` со значением null при ее вызове в обработчике завершения `__finally` для SEH, обработчике исключений `__except` или выражении фильтра `__except`.

Переданное исключение не поддерживает вложенные исключения. Вложенное исключение возникает, если во время обработки одного исключения возникает другое исключение. Если производится перехват вложенного исключения, данные-член `EXCEPTION_RECORD.ExceptionRecord` указывает на цепочку структур `EXCEPTION_RECORD`, описывающих соответствующие исключения. Функция `current_exception` не поддерживает вложенные исключения, поскольку она возвращает объект `exception_ptr`, данные-член `ExceptionRecord` которого обнулен.

Если производится перехват исключения SEH, необходимо обеспечить распределение памяти, на которую ссылается любой указатель в массиве данных-членов `EXCEPTION_RECORD.ExceptionInformation`. Необходимо гарантировать, что эта память действительна в течение времени существования соответствующего объекта `exception_ptr` и что эта память освобождается, когда объект `exception_ptr` удаляется.

Можно использовать функции преобразователя структурированного исключения (SE) вместе с функцией передачи исключений. Если исключение SEH преобразуется в исключение C++, функция `current_exception` возвращает `exception_ptr`, который ссылается на преобразованное исключение вместо исходного исключения SEH. Затем функция `rethrow_exception` вызывает преобразованное , а не исходное исключение. Дополнительные сведения о функции преобразователя SE. в разделе [_set_se_translator](../c-runtime-library/reference/set-se-translator.md).

## <a name="rethrowexception-function"></a>Функция rethrow_exception

После сохранения перехваченного исключения в объект `exception_ptr` основной поток может обработать этот объект. В основном потоке вызовите функцию `rethrow_exception`, указав объект `exception_ptr` в качестве аргумента. Функция `rethrow_exception` извлекает исключение из объекта `exception_ptr` и затем вызывает это исключение в контексте основного потока. Если `p` параметр `rethrow_exception` равно null, функция `exception_ptr`, функция создает [std::bad_exception](../standard-library/bad-exception-class.md).

Извлеченное исключение теперь является текущим исключением в основном потоке, и его можно обработать как любое другое исключение. При перехвате исключения можно обработать его незамедлительно или использовать оператор `throw` для отправки его в обработчик исключений верхнего уровня. В противном случае можно ничего не делать и позволить системному обработчику исключений по умолчанию завершить процесс.

## <a name="makeexceptionptr-function"></a>Функция make_exception_ptr

Функция `make_exception_ptr` принимает экземпляр класса в качестве аргумента и затем возвращает `exception_ptr`, который ссылается на этот экземпляр. Обычно объект [класс исключений](../standard-library/exception-class.md) указывается в качестве аргумента функции `make_exception_ptr`, однако аргументом может быть любой объект класса.

Вызов функции `make_exception_ptr` аналогичен созданию исключения C++, его перехвату в блоке `catch` дальнейшему вызову функции `current_exception` для возвращения объекта `exception_ptr`, ссылающегося на это исключение. Реализация Майкрософт для функции `make_exception_ptr` является более эффективной, чем создание и последующий перехват исключения.

Приложение обычно не требует функции `make_exception_ptr`, и мы не рекомендуем использовать ее.

## <a name="example"></a>Пример

В следующем примере стандартное исключение C++ и пользовательское исключение C++ передаются из одного потока в другой.

```cpp
// transport_exception.cpp
// compile with: /EHsc /MD
#include <windows.h>
#include <stdio.h>
#include <exception>
#include <stdexcept>

using namespace std;

// Define thread-specific information.
#define THREADCOUNT 2
exception_ptr aException[THREADCOUNT];
int           aArg[THREADCOUNT];

DWORD WINAPI ThrowExceptions( LPVOID );

// Specify a user-defined, custom exception.
// As a best practice, derive your exception
// directly or indirectly from std::exception.
class myException : public std::exception {
};
int main()
{
    HANDLE aThread[THREADCOUNT];
    DWORD ThreadID;

    // Create secondary threads.
    for( int i=0; i < THREADCOUNT; i++ )
    {
        aArg[i] = i;
        aThread[i] = CreateThread(
            NULL,       // Default security attributes.
            0,          // Default stack size.
            (LPTHREAD_START_ROUTINE) ThrowExceptions,
            (LPVOID) &aArg[i], // Thread function argument.
            0,          // Default creation flags.
            &ThreadID); // Receives thread identifier.
        if( aThread[i] == NULL )
        {
            printf("CreateThread error: %d\n", GetLastError());
            return -1;
        }
    }

    // Wait for all threads to terminate.
    WaitForMultipleObjects(THREADCOUNT, aThread, TRUE, INFINITE);
    // Close thread handles.
    for( int i=0; i < THREADCOUNT; i++ ) {
        CloseHandle(aThread[i]);
    }

    // Rethrow and catch the transported exceptions.
    for ( int i = 0; i < THREADCOUNT; i++ ) {
        try {
            if (aException[i] == NULL) {
                printf("exception_ptr %d: No exception was transported.\n", i);
            }
            else {
                rethrow_exception( aException[i] );
            }
        }
        catch( const invalid_argument & ) {
            printf("exception_ptr %d: Caught an invalid_argument exception.\n", i);
        }
        catch( const myException & ) {
            printf("exception_ptr %d: Caught a  myException exception.\n", i);
        }
    }
}
// Each thread throws an exception depending on its thread
// function argument, and then ends.
DWORD WINAPI ThrowExceptions( LPVOID lpParam )
{
    int x = *((int*)lpParam);
    if (x == 0) {
        try {
            // Standard C++ exception.
            // This example explicitly throws invalid_argument exception.
            // In practice, your application performs an operation that
            // implicitly throws an exception.
            throw invalid_argument("A C++ exception.");
        }
        catch ( const invalid_argument & ) {
            aException[x] = current_exception();
        }
    }
    else {
        // User-defined exception.
        aException[x] = make_exception_ptr( myException() );
    }
    return TRUE;
}
```

```Output
exception_ptr 0: Caught an invalid_argument exception.
exception_ptr 1: Caught a  myException exception.
```

## <a name="requirements"></a>Требования

**Заголовок:** \<exception>

## <a name="see-also"></a>См. также

- [Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)
- [/EH (модель обработки исключений)](../build/reference/eh-exception-handling-model.md)
- [/clr (компиляция среды выполнения)](../build/reference/clr-common-language-runtime-compilation.md)
