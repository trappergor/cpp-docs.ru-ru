---
title: Exception handling in MSVC
ms.date: 11/19/2019
helpviewer_keywords:
- try-catch keyword [C++], exception handling
ms.assetid: a6aa08de-669d-4ce8-9ec3-ec20d1354fcf
ms.openlocfilehash: 6cf71d6e6d0519951a084ebead65003bd363395f
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246591"
---
# <a name="exception-handling-in-msvc"></a>Exception handling in MSVC

Исключение — это условие ошибки, возможно вне элемента управления программы, которое не позволяет продолжать выполнение программы по обычному пути выполнения. Некоторые операции, включая создание объектов, ввод-вывод файлов и вызовы функций из других модулей, — это возможные источники исключений, даже если программа выполняется правильно. В надежном коде можно предвидеть и обработать исключения. To detect logic errors, use assertions rather than exceptions (see [Using Assertions](/visualstudio/debugger/c-cpp-assertions)).

## <a name="kinds-of-exceptions"></a>Kinds of exceptions

The Microsoft C++ compiler (MSVC) supports three kinds of exception handling:

- [C++ exception handling](errors-and-exception-handling-modern-cpp.md)

   В большинстве программ на языке C++ необходимо использовать обработку исключений C++, поскольку она является типобезопасной и гарантирует вызов деструкторов объектов во время очистки стека.

- [Structured exception handling](structured-exception-handling-c-cpp.md)

   Windows предоставляет собственный механизм исключений — SEH. Его не рекомендуется использовать при программировании C++ или MFC. Use SEH only in non-MFC C programs.

- [MFC exceptions](../mfc/exception-handling-in-mfc.md)

Use the [/EH](../build/reference/eh-exception-handling-model.md) compiler option to specify the type of exception handling to use in a project; C++ exception handling is the default. Не следует комбинировать механизмы обработки ошибок, например не следует использовать исключения C++ со структурированной обработкой исключений. Использование механизма обработки исключений языка C++ позволяет написать более переносимый код и обрабатывать исключения любого типа. For more information about the drawbacks of structured exception handling, see [Structured Exception Handling](structured-exception-handling-c-cpp.md). For advice about mixing MFC macros and C++ exceptions, see [Exceptions: Using MFC Macros and C++ Exceptions](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).

## <a name="in-this-section"></a>В данном разделе

- [Modern C++ best practices for exceptions and error handling](errors-and-exception-handling-modern-cpp.md)

- [How to design for exception safety](how-to-design-for-exception-safety.md)

- [How to interface between exceptional and non-exceptional code](how-to-interface-between-exceptional-and-non-exceptional-code.md)

- [The try, catch, and throw Statements](try-throw-and-catch-statements-cpp.md)

- [Проверка блоков Catch](how-catch-blocks-are-evaluated-cpp.md)

- [Exceptions and Stack Unwinding](exceptions-and-stack-unwinding-in-cpp.md)

- [Exception Specifications](exception-specifications-throw-cpp.md)

- [noexcept](noexcept-cpp.md)

- [Необработанные исключения C++](unhandled-cpp-exceptions.md)

- [Сочетание исключений C (структурированные) и C++](mixing-c-structured-and-cpp-exceptions.md)

- [Structured Exception Handling (SEH) (C/C++)](structured-exception-handling-c-cpp.md)

## <a name="see-also"></a>См. также

[Справочник по языку C++](cpp-language-reference.md)</br>
[Обработки исключений в 64-разрядных системах](../build/exception-handling-x64.md)</br>
[Exception Handling (C++/CLI and C++/CX)](../extensions/exception-handling-cpp-component-extensions.md)
