---
title: Оператор try-except
description: Ссылка на __try и __except структурированные операторы обработки исключений.
ms.date: 04/03/2020
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
ms.openlocfilehash: 132edf7cc9819637fafa3947686972d311924b99
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366239"
---
# <a name="try-except-statement"></a>Оператор try-except

Заявление **о попытке за исключением** — это расширение Майкрософт, поддерживающее структурированную обработку исключений на языках С и СЗ. Это расширение **специфична**для Microsoft.

## <a name="syntax"></a>Синтаксис

> **\_\_Попробовать**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;охраняемый код<br/>
> }<br/>
> за исключением *(выражение)* ** \_ \_**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;Код обработчика исключений<br/>
> }

## <a name="remarks"></a>Remarks

Заявление **о попытке за исключением** — это расширение корпорации Майкрософт на языках C и C. Это позволяет целевым приложениям получать контроль при событиях, которые обычно прекращают выполнение программы. Такие события называются *структурированные исключения,* или *исключения* для краткости. Механизм, который имеет дело с этими исключениями, называется *структурированной обработкой исключений* (SEH).

Для получения [соответствующей](../cpp/try-finally-statement.md)информации см.

Исключения могут быть как на аппаратном, так и на программном обеспечении. Структурированная обработка исключений полезна даже в том случае, если приложения не могут полностью восстановиться после исключения из аппаратного или программного обеспечения. SEH позволяет отображать информацию об ошибках и заманивать в ловушку внутреннее состояние приложения, чтобы помочь диагностировать проблему. Это особенно полезно для прерывистых проблем, которые не легко воспроизвести.

> [!NOTE]
> Структурированная обработка исключений поддерживается в Win32 для исходных файлов как на C, так и на C++. Тем не менее, он не специально разработан для СЗ. Для того чтобы ваш код лучше переносился, лучше использовать механизм обработки исключений языка C++. Кроме того, этот механизм отличается большей гибкостью, поскольку может обрабатывать исключения любого типа. Для программ СЗ мы рекомендуем использовать наирующее обращение с исключениями: [пробовать, ловить и бросать](../cpp/try-throw-and-catch-statements-cpp.md) операторы.

Соединение заявление после **__try** оговорка *тела* или *охраняемых* разделе. Выражение **__except** также известно как выражение *фильтра.* Его значение определяет способ обработки исключения. Соединение оператора после **__except** оговорки является обработчиком исключений. Обработчик определяет действия, которые необходимо предпринять, если при выполнении раздела тела возникает исключение. Выполнение происходит следующим образом:

1. Сначала выполняется защищенный раздел.

1. Если при выполнении охраняемого раздела не происходит никаких исключений, выполнение в заявлении продолжается после **__except** положения.

1. Если исключение происходит во время выполнения охраняемого раздела или в любой рутине, который вызывает охраняемый раздел, оценивается **__except** выражение. Возможны три значения.

   - `EXCEPTION_CONTINUE_EXECUTION`(-1) Исключение отменяется. Выполнение продолжается в точке, в которой возникло исключение.

   - `EXCEPTION_CONTINUE_SEARCH`(0) Исключение не признается. Программа переходит к поиску обработчика в стеке (сначала находятся выражения с оператором **try-except**, а затем обработчики со следующим наивысшим приоритетом).

   - `EXCEPTION_EXECUTE_HANDLER`(1) Исключение признается. Передача управления обработчику исключений путем выполнения **__except** сложной выписки, а затем продолжить выполнение после **__except** блока.

Выражение **__except** оценивается как выражение C. Она ограничена одним значением, оператором условного выражения или оператором запятой. Если требуется более сложная обработка, выражение может вызывать процедуру, которая возвращает одно из этих трех значений.

Каждое приложение может иметь свой собственный обработчик исключений.

Это не действительно, чтобы перейти в **__try** заявление, но действительно, чтобы выпрыгнуть из одного. Обработка исключений не вызывается, если процесс завершается в середине выполнения оператора **try-except.**

Для совместимости с предыдущими версиями, **_try,** **_except**и **_leave** являются синонимами для **__try,** **__except**и **__leave** если не указан вариант компилятора / [ \(Q Disable language extensions).](../build/reference/za-ze-disable-language-extensions.md)

### <a name="the-__leave-keyword"></a>Ключевое слово __leave

**Ключевое** __leave ключевое слово допустимо только в пределах охраняемого раздела оператора **try-except,** и его действие заключается в том, чтобы перейти к концу охраняемого раздела. Выполнение продолжается с первого оператора, следующего за обработчиком исключений.

Заявление **goto** также может выскочить из охраняемого раздела, и оно не ухудшает производительность, как это происходит в **try-finally.** Это потому, что стек раскручивания не происходит. Тем не менее, мы рекомендуем вам использовать **ключевое** слово __leave, а не **заявление goto.** Причина в том, что вы с меньшей вероятностью допустили ошибку в программировании, если охраняемый раздел большой или сложный.

### <a name="structured-exception-handling-intrinsic-functions"></a>Встроенные функции структурированной обработки исключений

Структурированная обработка исключений обеспечивает две внутренние функции, которые доступны для использования с **try-except** заявление: [GetExceptionCode](/windows/win32/Debug/getexceptioncode) и [GetExceptionInformation](/windows/win32/Debug/getexceptioninformation).

`GetExceptionCode`возвращает код (32-битный ряд) исключения.

Внутренняя функция `GetExceptionInformation` возвращает указатель в [EXCEPTION_POINTERS](/windows/win32/api/winnt/ns-winnt-exception_pointers) структуру, содержащую дополнительную информацию об исключении. Через этот указатель можно обращаться к состоянию компьютера, которое существовало в момент возникновения аппаратного исключения. Его структура выглядит следующим образом.

```cpp
typedef struct _EXCEPTION_POINTERS {
    PEXCEPTION_RECORD ExceptionRecord;
    PCONTEXT ContextRecord;
} EXCEPTION_POINTERS, *PEXCEPTION_POINTERS;
```

Типы `PEXCEPTION_RECORD` указателей `PCONTEXT` и определяются \<в файле winnt.h>, `_EXCEPTION_RECORD` и \< `_CONTEXT` определяются в файле excpt.h>

Можно использовать `GetExceptionCode` в обработчике исключений. Однако использовать `GetExceptionInformation` его можно только в рамках выражения фильтра исключений. Информация, на которая он указывает, обычно находится в стеке и больше не доступна при передаче элемента управления обработчику исключений.

Внутренняя функция [AbnormalTermination](/windows/win32/Debug/abnormaltermination) доступна в обработчике завершения. Он возвращает 0, если тело **try-finally** оператора прекращается последовательно. В остальных случаях функция возвращает 1.

\<excpt.h> определяет некоторые альтернативные имена для этих внутренностих:

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

## <a name="see-also"></a>См. также раздел

[Написание обработчика исключений](../cpp/writing-an-exception-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Keywords](../cpp/keywords-cpp.md)
