---
title: Оператор try-finally
ms.date: 11/19/2018
f1_keywords:
- __try
- _try
- __leave_cpp
- __leave
- __finally_cpp
- __try_cpp
- __finally
- _finally
helpviewer_keywords:
- __try keyword [C++]
- __finally keyword [C++]
- __leave keyword [C++]
- try-catch keyword [C++], try-finally keyword
- try-finally keyword [C++]
- __finally keyword [C++], try-finally statement syntax
- __leave keyword [C++], try-finally statement
- structured exception handling [C++], try-finally
ms.assetid: 826e0347-ddfe-4f6e-a7bc-0398e0edc7c2
ms.openlocfilehash: 045d2bf5617c81bcc4d7a202f36b112d5f0142a6
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246293"
---
# <a name="try-finally-statement"></a>Оператор try-finally

**Блок, относящийся только к системам Майкрософт**

The following syntax describes the **try-finally** statement:

> **\_\_try**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;// guarded code<br/>
> }<br/>
> **\_\_finally**<br/>
> {<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;// termination code<br/>
> }

## <a name="grammar"></a>Грамматика

*try-finally-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **\_\_try** *compound-statement* **\_\_finally** *compound-statement*

The **try-finally** statement is a Microsoft extension to the C and C++ languages that enables target applications to guarantee execution of cleanup code when execution of a block of code is interrupted. Очистка включает такие задачи, как отмена распределения памяти, закрытие файлов и освобождение их дескрипторов. The **try-finally** statement is especially useful for routines that have several places where a check is made for an error that could cause premature return from the routine.

For related information and a code sample, see [try-except Statement](../cpp/try-except-statement.md). For more information on structured exception handling in general, see [Structured Exception Handling](../cpp/structured-exception-handling-c-cpp.md). For more information on handling exceptions in managed applications with C++/CLI, see [Exception Handling under /clr](../extensions/exception-handling-cpp-component-extensions.md).

> [!NOTE]
> Структурированная обработка исключений поддерживается в Win32 для исходных файлов как на C, так и на C++. Однако она не предназначена специально для C++. Для того чтобы ваш код лучше переносился, лучше использовать механизм обработки исключений языка C++. Кроме того, этот механизм отличается большей гибкостью, поскольку может обрабатывать исключения любого типа. For C++ programs, it is recommended that you use the C++ exception-handling mechanism ([try, catch, and throw](../cpp/try-throw-and-catch-statements-cpp.md) statements).

The compound statement after the **__try** clause is the guarded section. The compound statement after the **__finally** clause is the termination handler. Такой обработчик определяет набор действий, выполняемых при выходе из защищенного раздела независимо от того, происходит ли выход в результате исключения (ненормальное завершение) или в результате стандартной передачи управления дальше (нормальное завершение).

Control reaches a **__try** statement by simple sequential execution (fall through). When control enters the **__try**, its associated handler becomes active. Если поток элементов управления достигает конца блока try, выполнение продолжается следующим образом.

1. Вызывается обработчик завершения.

1. When the termination handler completes, execution continues after the **__finally** statement. Regardless of how the guarded section ends (for example, via a **goto** out of the guarded body or a **return** statement), the termination handler is executed *before* the flow of control moves out of the guarded section.

   A **__finally** statement does not block searching for an appropriate exception handler.

If an exception occurs in the **__try** block, the operating system must find a handler for the exception or the program will fail. If a handler is found, any and all **__finally** blocks are executed and execution resumes in the handler.

Например, предположим, ряд вызовов функций связывает функцию А с функцией D, как показано на следующем рисунке. Каждая функция имеет один обработчик завершения. Если исключение создается в функции D и обрабатывается в функции А, обработчики завершения вызываются в том порядке, в котором система освобождает стек: D, C и B.

![Order of termination&#45;handler execution](../cpp/media/vc38cx1.gif "Order of termination&#45;handler execution") <br/>
Порядок выполнения обработчиков завершения

> [!NOTE]
> The behavior of try-finally is different from some other languages that support the use of **finally**, such as C#.  A single **__try** may have either, but not both, of **__finally** and **__except**.  Если оба следует использовать одновременно, оператор try-except должен включать внутренней оператор try-finally.  Правила,задающие время выполнения каждого блока, также различаются.

For compatibility with previous versions, **_try**, **_finally**, and **_leave** are synonyms for **__try**, **__finally**, and **__leave** unless compiler option [/Za \(Disable language extensions)](../build/reference/za-ze-disable-language-extensions.md) is specified.

## <a name="the-__leave-keyword"></a>Ключевое слово __leave

The **__leave** keyword is valid only within the guarded section of a **try-finally** statement, and its effect is to jump to the end of the guarded section. Выполнение продолжается с первого оператора в обработчике завершения.

A **goto** statement can also jump out of the guarded section, but it degrades performance because it invokes stack unwinding. The **__leave** statement is more efficient because it does not cause stack unwinding.

## <a name="abnormal-termination"></a>Аварийное завершение

Exiting a **try-finally** statement using the [longjmp](../c-runtime-library/reference/longjmp.md) run-time function is considered abnormal termination. It is illegal to jump into a **__try** statement, but legal to jump out of one. All **__finally** statements that are active between the point of departure (normal termination of the **__try** block) and the destination (the **__except** block that handles the exception) must be run. Это называется "локальной раскруткой".

If a **try** block is prematurely terminated for any reason, including a jump out of the block, the system executes the associated **finally** block as a part of the process of unwinding the stack. In such cases, the [AbnormalTermination](/windows/win32/Debug/abnormaltermination) function returns **true** if called from within the **finally** block; otherwise, it returns **false**.

The termination handler is not called if a process is killed in the middle of executing a **try-finally** statement.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Writing a termination handler](../cpp/writing-a-termination-handler.md)<br/>
[Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Termination-Handler Syntax](/windows/win32/Debug/termination-handler-syntax)