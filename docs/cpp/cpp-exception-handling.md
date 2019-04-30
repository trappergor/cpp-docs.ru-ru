---
title: Обработка исключений С++
ms.date: 11/04/2016
helpviewer_keywords:
- C++ exception handling
- Visual C++, exception handling
ms.assetid: 65f80b44-9d0f-4d17-b910-07205a5c5c40
ms.openlocfilehash: b4eaab7d5bb352cccc612dd950572464b82b67e8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392314"
---
# <a name="c-exception-handling"></a>Обработка исключений С++

Язык C++ предоставляет встроенную поддержку для создания и перехвата исключений. При программировании на C++ почти всегда необходимо использовать встроенную поддержку исключений C++, как описано в этом разделе.

Чтобы включить обработку исключений C++ в коде, используйте [/EHsc](../build/reference/eh-exception-handling-model.md).

## <a name="in-this-section"></a>В этом разделе

В этом описании обработки исключений C++ рассматриваются:

- [Try, catch и throw-операторы](../cpp/try-throw-and-catch-statements-cpp.md)

- [Проверка блоков Catch](../cpp/how-catch-blocks-are-evaluated-cpp.md)

- [Исключения и очистка стека](../cpp/exceptions-and-stack-unwinding-in-cpp.md)

- [Спецификации исключений](../cpp/exception-specifications-throw-cpp.md)

- [noexcept](../cpp/noexcept-cpp.md)

- [Необработанные исключения C++](../cpp/unhandled-cpp-exceptions.md)

- [Сочетание исключений C (структурированные) и C++](../cpp/mixing-c-structured-and-cpp-exceptions.md)

## <a name="support-for-earlier-mfc-exceptions"></a>Поддержка более ранних исключений MFC

Начиная с версии 4.0, MFC использует механизм обработки исключений C++. Хотя настоятельно рекомендуется использовать обработку исключений C++ в новом коде, версии MFC 4.0 и выше сохраняют макросы из предыдущих версий MFC, чтобы старый код не пострадал. Макросы и новый механизм также могут сочетаться. Сведения о сочетании макросов и C++ исключение обработку и о преобразовании старого кода для использования нового механизма, см. в статьях [исключения: Использование макросов MFC и C++ исключения](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) и [исключения: Преобразование из макроса исключений MFC](../mfc/exceptions-converting-from-mfc-exception-macros.md). Более ранние макросы исключений MFC, если вы их еще используете, возвращают ключевые слова исключений C++. См. в разделе [исключения: Изменения в макросах исключений в версии 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md).

## <a name="see-also"></a>См. также

[Обработка исключений](../cpp/exception-handling-in-visual-cpp.md)