---
title: Ограничения, действующие в отношении обработчиков исключений
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 54bf4a44d06eacd22dc4b9819d160d3c6a66c684
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179085"
---
# <a name="restrictions-on-exception-handlers"></a>Ограничения, действующие в отношении обработчиков исключений

Основным ограничением использования обработчиков исключений в коде является то, что нельзя использовать оператор **goto** для перехода в блок инструкций **__try** . Входить в этот блок необходимо только через обычный поток управления. Можно выйти из блока инструкций **__try** и вложенных обработчиков исключений по мере выбора.

## <a name="see-also"></a>См. также раздел

[Написание обработчика исключений](../cpp/writing-an-exception-handler.md)<br/>
[Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
