---
title: Оператор try-except
ms.date: 10/09/2018
f1_keywords:
- _abnormal_termination_cpp
- _exception_code_cpp
- _exception_info
- __except
- _except
- _exception_code
- __except_cpp
- _exception_info_cpp
helpviewer_keywords:
- __try keyword [C++]
- EXCEPTION_CONTINUE_EXECUTION macro
- EXCEPTION_CONTINUE_SEARCH macro
- EXCEPTION_EXECUTE_HANDLER macro
- GetExceptionCode function
- try-catch keyword [C++], try-except keyword [C++]
- _exception_code keyword [C++]
- try-except keyword [C++]
- _exception_info keyword [C++]
- _abnormal_termination keyword [C++]
ms.assetid: 30d60071-ea49-4bfb-a8e6-7a420de66381
ms.openlocfilehash: 7d3a92aa8c6d1f77a1795eabde0ae1e575bb5770
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444127"
---
# <a name="try-except-statement"></a>Оператор try-except

**Блок, относящийся только к системам Microsoft**

Оператор **try-except** — это расширение Майкрософт для C и C++ языков, поддерживающих структурированную обработку исключений.

## <a name="syntax"></a>Синтаксис

> **\_\_попробуйте**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;//защищенный код<br/>
> }<br/>
> **\_\_except** ( *выражение* )<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;//код обработчика исключений<br/>
> }

## <a name="remarks"></a>Remarks

Оператор **try-except** — это расширение Майкрософт для C и C++ языков, которое позволяет целевым приложениям получать контроль над событиями, которые обычно приводят к завершению выполнения программы. Такие события называются *исключениями*, а механизм, который обрабатывает исключения, называется *структурной обработкой исключений* (SEH).

Связанные сведения см. в описании [оператора try-finally](../cpp/try-finally-statement.md).

Исключения могут быть аппаратными или программными. Даже если работа приложения после таких исключений и не может полностью восстановиться, структурированная обработка исключений позволяет отобразить информацию об ошибке и зафиксировать внутреннее состояние приложения, чтобы выполнить диагностику проблемы. Это особенно полезно для нерегулярно встречающихся неполадок, которые сложно воспроизвести.

> [!NOTE]
> Структурированная обработка исключений поддерживается в Win32 для исходных файлов как на C, так и на C++. Однако она не предназначена специально для C++. Для того чтобы ваш код лучше переносился, лучше использовать механизм обработки исключений языка C++. Кроме того, этот механизм отличается большей гибкостью, поскольку может обрабатывать исключения любого типа. Для C++ программ рекомендуется использовать механизм обработки C++ исключений (операторы[try, catch и Throw](../cpp/try-throw-and-catch-statements-cpp.md) ).

Составной оператор после предложения **__try** — тело или защищенный раздел. Составной оператор после предложения **__except** является обработчиком исключений. Он задает набор действий, выполняемых при возникновении исключения в теле защищенного раздела. Выполнение происходит следующим образом:

1. Сначала выполняется защищенный раздел.

1. Если во время выполнения защищенного раздела исключение не возникает, выполнение продолжится в операторе после предложения **__except** .

1. Если исключение возникает во время выполнения защищенного раздела или в любой подпрограмме, вызванном вызовом защищенного раздела, вычисляется **__except** *выражение* (называемое критерием *фильтра* ), а значение определяет, как обрабатываются исключения. Возможны три значения.

   - EXCEPTION_CONTINUE_EXECUTION (-1) исключение отклонено. Выполнение продолжается в точке, в которой возникло исключение.

   - EXCEPTION_CONTINUE_SEARCH (0) исключение не распознано. Программа переходит к поиску обработчика в стеке (сначала находятся выражения с оператором **try-except**, а затем обработчики со следующим наивысшим приоритетом).

   - Распознано исключение EXCEPTION_EXECUTE_HANDLER (1). Передайте управление обработчику исключений, выполнив составной оператор **__except** , а затем продолжайте выполнение после блока **__except** .

Так как выражение **__except** вычисляется как выражение C, оно ограничено одним значением, оператором условного выражения или оператором-запятой. Если требуется более сложная обработка, выражение может вызывать процедуру, которая возвращает одно из этих трех значений.

Каждое приложение может иметь свой собственный обработчик исключений.

Переход к оператору **__try** невозможен, но он является допустимым для перехода из одной инструкции. Обработчик исключений не вызывается, если процесс завершается в процессе выполнения инструкции **try-except** .

Для совместимости с предыдущими версиями **_try**, **_except**и **_leave** являются синонимами для **__try**, **__except**и **__leave** , если не задан параметр компилятора [/Za \(отключить расширения языка)](../build/reference/za-ze-disable-language-extensions.md) .

### <a name="the-__leave-keyword"></a>Ключевое слово __leave

Ключевое слово **__leave** допустимо только в защищенном разделе оператора **try-except** , и его результат заключается в переходе к концу защищенного раздела. Выполнение продолжается с первого оператора, следующего за обработчиком исключений.

Оператор **goto** также может выйти из защищенного раздела и не ухудшит производительность, как это делается в операторе **try-finally** , так как очистка стека не выполняется. Однако рекомендуется использовать ключевое слово **__leave** , а не инструкцию **goto** , так как вероятность того, что вы менее вероятно, сделаете ошибку программирования, если защищенный раздел является большим или сложным.

### <a name="structured-exception-handling-intrinsic-functions"></a>Встроенные функции структурированной обработки исключений

Структурированная обработка исключений предоставляет две встроенные функции, которые можно использовать с оператором **try-except** : `GetExceptionCode` и `GetExceptionInformation`.

`GetExceptionCode` возвращает код (32-разрядное целое число) исключения.

Встроенная функция `GetExceptionInformation` возвращает указатель на структуру, содержащую дополнительные сведения об исключении. Через этот указатель можно обращаться к состоянию компьютера, которое существовало в момент возникновения аппаратного исключения. Его структура выглядит следующим образом.

```cpp
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS;
```

Типы указателей `PEXCEPTION_RECORD` и `PCONTEXT` определены во включаемом файле \<Winnt. h >, а `_EXCEPTION_RECORD` и `_CONTEXT` определяются в включаемом файле \<екскпт. h >

В обработчике исключений можно использовать `GetExceptionCode`. Однако `GetExceptionInformation` можно использовать только в выражении фильтра исключений. Обычно она указывает на сведения, которые хранятся в стеке и уже недоступны в тот момент, когда управление передаются обработчику исключений.

Встроенная функция `AbnormalTermination` доступна в обработчике завершения. Он возвращает 0, если тело оператора **try-finally** завершается последовательно. В остальных случаях функция возвращает 1.

екскпт. h определяет некоторые альтернативные имена для этих встроенных функций:

`GetExceptionCode` — это эквивалент `_exception_code`

`GetExceptionInformation` — это эквивалент `_exception_info`

`AbnormalTermination` — это эквивалент `_abnormal_termination`

## <a name="example"></a>Пример

```cpp
// exceptions_try_except_Statement.cpp
// Example of try-except and try-finally statements
#include <stdio.h>
#include <windows.h> // for EXCEPTION_ACCESS_VIOLATION
#include <excpt.h>

int filter(unsigned int code, struct _EXCEPTION_POINTERS *ep)
{
    puts("in filter.");
    if (code == EXCEPTION_ACCESS_VIOLATION)
    {
        puts("caught AV as expected.");
        return EXCEPTION_EXECUTE_HANDLER;
    }
    else
    {
        puts("didn't catch AV, unexpected.");
        return EXCEPTION_CONTINUE_SEARCH;
    };
}

int main()
{
    int* p = 0x00000000;   // pointer to NULL
    puts("hello");
    __try
    {
        puts("in try");
        __try
        {
            puts("in try");
            *p = 13;    // causes an access violation exception;
        }
        __finally
        {
            puts("in finally. termination: ");
            puts(AbnormalTermination() ? "\tabnormal" : "\tnormal");
        }
    }
    __except(filter(GetExceptionCode(), GetExceptionInformation()))
    {
        puts("in except");
    }
    puts("world");
}
```

### <a name="output"></a>Выходные данные

```Output
hello
in try
in try
in filter.
caught AV as expected.
in finally. termination:
        abnormal
in except
world
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[Написание обработчика исключений](../cpp/writing-an-exception-handler.md)<br/>
[Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
