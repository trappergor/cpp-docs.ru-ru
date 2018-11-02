---
title: Написание обработчика исключений
ms.date: 11/04/2016
helpviewer_keywords:
- structured exception handling [C++], exception handlers
- exception handling [C++], exception handlers
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
ms.openlocfilehash: 6f1bcecf3aaed2bf2b7ebbe511f11cdb5ec1ca5e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644786"
---
# <a name="writing-an-exception-handler"></a>Написание обработчика исключений

Обработчики исключений обычно используются для ответа на конкретные ошибки. Можно использовать синтаксис обработки исключений, чтобы фильтровать все исключения, отличные от тех, которые вы знаете, как обработать. Прочие исключения должны передаваться другим обработчикам (возможно, в библиотеке среды выполнения или ОС), созданным для поиска этих конкретных исключений.

Обработчики исключений используют оператор try-except.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Try-except инструкции](../cpp/try-except-statement.md)

- [Написание фильтра исключений](../cpp/writing-an-exception-filter.md)

- [Создание исключений программного обеспечения](../cpp/raising-software-exceptions.md)

- [Исключения оборудования](../cpp/hardware-exceptions.md)

- [Ограничения обработчиков исключений](../cpp/restrictions-on-exception-handlers.md)

## <a name="see-also"></a>См. также

[Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)