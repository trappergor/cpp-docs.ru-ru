---
title: Написание обработчика исключений
ms.date: 11/04/2016
helpviewer_keywords:
- structured exception handling [C++], exception handlers
- exception handling [C++], exception handlers
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
ms.openlocfilehash: 201dcaa6a90584d1f9535df11d5722a37bdceb89
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187288"
---
# <a name="writing-an-exception-handler"></a>Написание обработчика исключений

Обработчики исключений обычно используются для ответа на конкретные ошибки. Можно использовать синтаксис обработки исключений, чтобы фильтровать все исключения, отличные от тех, которые вы знаете, как обработать. Прочие исключения должны передаваться другим обработчикам (возможно, в библиотеке среды выполнения или ОС), созданным для поиска этих конкретных исключений.

Обработчики исключений используют оператор try-except.

## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения

- [Оператор try-except](../cpp/try-except-statement.md)

- [Написание фильтра исключений](../cpp/writing-an-exception-filter.md)

- [Создание исключений программного обеспечения](../cpp/raising-software-exceptions.md)

- [Исключения оборудования](../cpp/hardware-exceptions.md)

- [Ограничения обработчиков исключений](../cpp/restrictions-on-exception-handlers.md)

## <a name="see-also"></a>См. также раздел

[Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
