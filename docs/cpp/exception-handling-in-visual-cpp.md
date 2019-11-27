---
title: Обработка исключений в КОМПИЛЯТОРОМ MSVC
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
# <a name="exception-handling-in-msvc"></a>Обработка исключений в КОМПИЛЯТОРОМ MSVC

Исключение — это условие ошибки, возможно вне элемента управления программы, которое не позволяет продолжать выполнение программы по обычному пути выполнения. Некоторые операции, включая создание объектов, ввод-вывод файлов и вызовы функций из других модулей, — это возможные источники исключений, даже если программа выполняется правильно. В надежном коде можно предвидеть и обработать исключения. Для обнаружения логических ошибок используйте утверждения, а не исключения (см. раздел [использование утверждений](/visualstudio/debugger/c-cpp-assertions)).

## <a name="kinds-of-exceptions"></a>Виды исключений

Microsoft C++ COMPILER (компилятором MSVC) поддерживает три типа обработки исключений:

- [C++Обработка исключений](errors-and-exception-handling-modern-cpp.md)

   В большинстве программ на языке C++ необходимо использовать обработку исключений C++, поскольку она является типобезопасной и гарантирует вызов деструкторов объектов во время очистки стека.

- [Структурированная обработка исключений](structured-exception-handling-c-cpp.md)

   Windows предоставляет собственный механизм исключений — SEH. Его не рекомендуется использовать при программировании C++ или MFC. SEH следует использовать только в программах C, не относящихся к MFC.

- [Исключения MFC](../mfc/exception-handling-in-mfc.md)

Используйте параметр компилятора [/EH](../build/reference/eh-exception-handling-model.md) , чтобы указать тип обработки исключений для использования в проекте. C++ по умолчанию используется обработка исключений. Не следует комбинировать механизмы обработки ошибок, например не следует использовать исключения C++ со структурированной обработкой исключений. Использование механизма обработки исключений языка C++ позволяет написать более переносимый код и обрабатывать исключения любого типа. Дополнительные сведения о недостатках структурированной обработки исключений см. в разделе [структурированная обработка исключений](structured-exception-handling-c-cpp.md). Рекомендации по смешению макросов и C++ исключений MFC см. в разделе [исключения: использование C++ макросов и исключений MFC](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md).

## <a name="in-this-section"></a>В этом разделе

- [Современные C++ рекомендации по исключениям и обработке ошибок](errors-and-exception-handling-modern-cpp.md)

- [Разработка для обеспечения безопасности исключений](how-to-design-for-exception-safety.md)

- [Как взаимодействовать между исключительным и неисключительным кодом](how-to-interface-between-exceptional-and-non-exceptional-code.md)

- [Операторы Try, catch и Throw](try-throw-and-catch-statements-cpp.md)

- [Проверка блоков Catch](how-catch-blocks-are-evaluated-cpp.md)

- [Исключения и очистка стека](exceptions-and-stack-unwinding-in-cpp.md)

- [Спецификации исключений](exception-specifications-throw-cpp.md)

- [noexcept](noexcept-cpp.md)

- [Необработанные исключения C++](unhandled-cpp-exceptions.md)

- [Сочетание исключений C (структурированные) и C++](mixing-c-structured-and-cpp-exceptions.md)

- [Структурированная обработка исключений (SEH) (CC++/)](structured-exception-handling-c-cpp.md)

## <a name="see-also"></a>См. также:

[Справочник по языку C++](cpp-language-reference.md)</br>
[Обработки исключений в 64-разрядных системах](../build/exception-handling-x64.md)</br>
[Обработка исключений (C++/CLI и C++/CX)](../extensions/exception-handling-cpp-component-extensions.md)
