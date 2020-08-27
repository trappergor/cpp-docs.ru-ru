---
title: Ограничения обработчиков исключений
description: Описывает ограничения по переходу в структурированные блоки обработки исключений.
ms.date: 08/24/2020
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: c4182f065789533bf7599621d8d2829b2d52d6ed
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898451"
---
# <a name="restrictions-on-exception-handlers"></a>Ограничения обработчиков исключений

Основным ограничением использования обработчиков исключений в коде является то, что нельзя использовать **`goto`** оператор для перехода в **`__try`** блок операторов. Входить в этот блок необходимо только через обычный поток управления. Можно выйти из **`__try`** блока операторов, и вы можете вкладывать обработчики исключений по своему выбору.

## <a name="see-also"></a>См. также

[Написание обработчика исключений](../cpp/writing-an-exception-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
