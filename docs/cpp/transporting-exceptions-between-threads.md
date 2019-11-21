---
title: Перенос исключений между потоками
ms.date: 05/07/2019
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
ms.openlocfilehash: 25b09c508b932a4d1470f6b23f03aa52e62c68cc
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246315"
---
# <a name="transporting-exceptions-between-threads"></a>Перенос исключений между потоками

The Microsoft C++ compiler (MSVC) supports *transporting an exception* from one thread to another. Передача исключений позволяет перехватывать исключение в одном потоке и затем обеспечить видимость того, что исключение возникло в другом потоке. Например, эту возможность можно использовать для создания многопоточного приложения, где первостепенный поток обрабатывает все исключения, создаваемые его второстепенными потоками. Передача исключений в основном полезна для разработчиков, создающих системы или библиотеки параллельного программирования. To implement transporting exceptions, MSVC provides the [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) type and the [current_exception](../standard-library/exception-functions.md#current_exception), [rethrow_exception](../standard-library/exception-functions.md#rethrow_exception), and [make_exception_ptr](../standard-library/exception-functions.md#make_exception_ptr) functions.

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

|Параметр|Описание|
|---------------|-----------------|
|*unspecified*|Неуказанный внутренний класс, используемый для реализации типа `exception_ptr`.|
|*p*|Объект `exception_ptr`, который ссылается на исключение.|
|*E*|Класс, представляющий исключение.|
|*e*|Экземпляр класса `E` параметров.|

## <a name="return-value"></a>Возвращаемое значение

Функция `current_exception` возвращает объект `exception_ptr`, который ссылается на исключение, выполняемое в данный момент. Если никакое исключение не выполняется, функция возвращает объект `exception_ptr`, не связанный ни с одним исключением.

The `make_exception_ptr` function returns an `exception_ptr` object that references the exception specified by the *e* parameter.

## <a name="remarks"></a>Заметки

### <a name="scenario"></a>Сценарий

Предположим, что требуется создать приложение, которое может масштабироваться для выполнения переменного объема работы. Для достижения этой цели создается многопоточное приложение, где исходный основной поток создает столько второстепенных потоков, сколько необходимо для выполнения задачи. Второстепенные потоки помогают первичному потоку распоряжаться ресурсами, распределять нагрузку и повышать пропускную способность. Благодаря распределению работы многопоточное приложение работает быстрее, чем однопоточное.

Однако если второстепенный поток вызывает исключение, необходимо обеспечить его обработку основным потоком. Это обусловлено тем, что требуется обеспечить обработку исключений приложением единообразным, унифицированным способом независимо от количества второстепенных потоков.

### <a name="solution"></a>Решение

Для выполнения указанного выше сценария стандарт C++ поддерживает передачу исключений между потоками. If a secondary thread throws an exception, that exception becomes the *current exception*. By analogy to the real world, the current exception is said to be *in flight*. Текущее исключение находится в полете со времени создания до возвращения результата обработчиком исключений, перехватывающим его.

The secondary thread can catch the current exception in a **catch** block, and then call the `current_exception` function to store the exception in an `exception_ptr` object. Объект `exception_ptr` должен быть доступным для второстепенного и первичного потоков. Например, объект `exception_ptr` может быть глобальной переменной, доступ к который регулируется мьютексом. The term *transport an exception* means an exception in one thread can be converted to a form that can be accessed by another thread.

Далее основной поток вызывает функцию `rethrow_exception`, которая извлекает исключение из объекта `exception_ptr` и затем вызывает его. При вызове исключения оно становится текущим исключением в основном потоке. Это означает, что создается видимость того, что исключение возникает в основном потоке.

Finally, the primary thread can catch the current exception in a **catch** block and then process it or throw it to a higher level exception handler. Также основной поток может проигнорировать исключение и позволить процессу завершиться.

Большинству приложений не требуется передавать исключения между потоками. Однако эта возможность полезна в системе параллельных вычислений, поскольку система может распределить работу между второстепенными потоками, процессорами или ядрами. В среде параллельных вычислений один выделенный поток может обрабатывать все исключения из второстепенных потоков и может предоставлять единообразную модель обработки исключений любому приложению.

Дополнительные сведения о предложении Комитета по стандартам C++ можно получить, найдя в Интернете документ с номером N2179 «Поддержка передачи исключений между потоками в языке».

### <a name="exception-handling-models-and-compiler-options"></a>Exception-handling models and compiler options

Модель обработки исключений приложения определяет, возможен ли в нем перехват и передача исключения. Visual C++ поддерживает 3 модели, которые могут обрабатывать исключения C++, исключения структурированной обработки (SEH) и исключения среды CLR. Use the [/EH](../build/reference/eh-exception-handling-model.md) and [/clr](../build/reference/clr-common-language-runtime-compilation.md) compiler options to specify your application's exception-handling model.

Только следующее сочетание параметров компилятора и операторов программирования может передавать исключение. Другие сочетания либо не могут перехватывать исключения, либо могут перехватывать, но не могут передавать исключения.

- The **/EHa** compiler option and the **catch** statement can transport SEH and C++ exceptions.

- The **/EHa**, **/EHs**, and **/EHsc** compiler options and the **catch** statement can transport C++ exceptions.

- The **/CLR** compiler option and the **catch** statement can transport C++ exceptions. The **/CLR** compiler option implies specification of the **/EHa** option. Обратите внимание, что компилятор не поддерживает передачу управляемых исключений. This is because managed exceptions, which are derived from the [System.Exception class](../standard-library/exception-class.md), are already objects that you can move between threads by using the facilities of the common languange runtime.

   > [!IMPORTANT]
   > We recommend that you specify the **/EHsc** compiler option and catch only C++ exceptions. You expose yourself to a security threat if you use the **/EHa** or **/CLR** compiler option and a **catch** statement with an ellipsis *exception-declaration* (`catch(...)`). You probably intend to use the **catch** statement to capture a few specific exceptions. Однако оператор `catch(...)` перехватывает все исключения C++ и SEH, включая непредвиденные, которые должны приводить к сбою. Если непредвиденное исключение игнорируется или обрабатывается неверно, вредоносный код может использовать эту возможность, чтобы подорвать безопасность программы.

## <a name="usage"></a>Использование

The following sections describe how to transport exceptions by using the `exception_ptr` type, and the `current_exception`, `rethrow_exception`, and `make_exception_ptr` functions.

## <a name="exception_ptr-type"></a>exception_ptr type

Используйте объект `exception_ptr` для ссылки на текущее исключение или экземпляр указанного пользователем исключения. В реализации Майкрософт исключение представлено структурой [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record). Каждый объект `exception_ptr` содержит поле ссылки на исключение, указывающее на копию структуры `EXCEPTION_RECORD`, представляющую исключение.

При объявлении переменной `exception_ptr` эта переменная не связана ни с одним исключением. То есть в поле ссылки на исключение находится значение NULL. Такой объект `exception_ptr` называется *exception_ptr null*.

Используйте функцию `current_exception` или `make_exception_ptr` для назначения исключения объекту `exception_ptr`. При назначении исключения переменной `exception_ptr` поле ссылки на исключение переменной указывает на копию исключения. При нехватке памяти для копирования исключения поле ссылки на исключение указывает на копию исключения [std::bad_alloc](../standard-library/bad-alloc-class.md). If the `current_exception` or `make_exception_ptr` function cannot copy the exception for any other reason, the function calls the [terminate](../c-runtime-library/reference/terminate-crt.md) function to exit the current process.

Несмотря на свое имя, объект `exception_ptr` не является указателем. It does not obey pointer semantics and cannot be used with the pointer member access (`->`) or indirection (`*`) operators. Объект `exception_ptr` не имеет открытых данных-членов и функций-членов.

### <a name="comparisons"></a>Сравнения

Можно использовать операторы равенства (`==`) и неравенства (`!=`) для сравнения двух объектов `exception_ptr`. Эти операторы не сравнивают бинарное значение (битовый шаблон) структур `EXCEPTION_RECORD`, которые представляют исключения. Вместо этого операторы сравнивают адреса в поле ссылки на исключение объектов `exception_ptr`. Поэтому `exception_ptr` со значением null и значение NULL при сравнении считаются равными.

## <a name="current_exception-function"></a>current_exception function

Call the `current_exception` function in a **catch** block. If an exception is in flight and the **catch** block can catch the exception, the `current_exception` function returns an `exception_ptr` object that references the exception. В противном случае функция возвращает объект `exception_ptr` со значением null.

### <a name="details"></a>Подробнее

The `current_exception` function captures the exception that is in flight regardless of whether the **catch** statement specifies an [exception-declaration](../cpp/try-throw-and-catch-statements-cpp.md) statement.

The destructor for the current exception is called at the end of the **catch** block if you do not rethrow the exception. Но даже при вызове функции `current_exception` в деструкторе эта функция возвращает объект `exception_ptr`, который ссылается на текущее исключение.

Последующие вызовы функции `current_exception` возвращают объекты `exception_ptr`, которые ссылаются на различные копии текущего исключения. Соответственно, при сравнении объекты не признаются равными, поскольку они ссылаются на различные копии, даже если эти копии имеют одинаковые бинарные значения.

### <a name="seh-exceptions"></a>SEH exceptions

If you use the **/EHa** compiler option, you can catch an SEH exception in a C++ **catch** block. Функция `current_exception` возвращает объект `exception_ptr`, который ссылается на исключение SEH. And the `rethrow_exception` function throws the SEH exception if you call it with thetransported `exception_ptr` object as its argument.

The `current_exception` function returns a null `exception_ptr` if you call it in an SEH **__finally** termination handler, an **__except** exception handler, or the **__except** filter expression.

Переданное исключение не поддерживает вложенные исключения. Вложенное исключение возникает, если во время обработки одного исключения возникает другое исключение. Если производится перехват вложенного исключения, данные-член `EXCEPTION_RECORD.ExceptionRecord` указывает на цепочку структур `EXCEPTION_RECORD`, описывающих соответствующие исключения. Функция `current_exception` не поддерживает вложенные исключения, поскольку она возвращает объект `exception_ptr`, данные-член `ExceptionRecord` которого обнулен.

Если производится перехват исключения SEH, необходимо обеспечить распределение памяти, на которую ссылается любой указатель в массиве данных-членов `EXCEPTION_RECORD.ExceptionInformation`. Необходимо гарантировать, что эта память действительна в течение времени существования соответствующего объекта `exception_ptr` и что эта память освобождается, когда объект `exception_ptr` удаляется.

Можно использовать возможности преобразователя структурированного исключения (SE) вместе с возможностью передачи исключений. Если исключение SEH преобразуется в исключение C++, функция `current_exception` возвращает `exception_ptr`, который ссылается на преобразованное исключение вместо исходного исключения SEH. Затем функция `rethrow_exception` вызывает преобразованное , а не исходное исключение. For more information about SE translator functions, see [_set_se_translator](../c-runtime-library/reference/set-se-translator.md).

## <a name="rethrow_exception-function"></a>rethrow_exception function

После сохранения перехваченного исключения в объект `exception_ptr` основной поток может обработать этот объект. В основном потоке вызовите функцию `rethrow_exception`, указав объект `exception_ptr` в качестве аргумента. Функция `rethrow_exception` извлекает исключение из объекта `exception_ptr` и затем вызывает это исключение в контексте основного потока. If the *p* parameter of the `rethrow_exception` function is a null `exception_ptr`, the function throws [std::bad_exception](../standard-library/bad-exception-class.md).

Извлеченное исключение теперь является текущим исключением в основном потоке, и его можно обработать как любое другое исключение. If you catch the exception, you can handle it immediately or use a **throw** statement to send it to a higher level exception handler. В противном случае можно ничего не делать и позволить системному обработчику исключений по умолчанию завершить процесс.

## <a name="make_exception_ptr-function"></a>Функция make_exception_ptr

Функция `make_exception_ptr` принимает экземпляр класса в качестве аргумента и затем возвращает `exception_ptr`, который ссылается на этот экземпляр. Обычно объект [класс исключений](../standard-library/exception-class.md) указывается в качестве аргумента функции `make_exception_ptr`, однако аргументом может быть любой объект класса.

Calling the `make_exception_ptr` function is equivalent to throwing a C++ exception, catching it in a **catch** block, and then calling the `current_exception` function to return an `exception_ptr` object that references the exception. Реализация Майкрософт для функции `make_exception_ptr` является более эффективной, чем создание и последующий перехват исключения.

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

[Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)<br/>
[/EH (модель обработки исключений)](../build/reference/eh-exception-handling-model.md)<br/>
[/clr (компиляция среды выполнения)](../build/reference/clr-common-language-runtime-compilation.md)
