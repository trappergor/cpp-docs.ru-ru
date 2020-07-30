---
title: Ограничения обработчиков исключений
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 1f80cb1574cbfef0783c7e55dcd198dfb822f566
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225908"
---
# <a name="restrictions-on-exception-handlers"></a>Ограничения обработчиков исключений

Основным ограничением использования обработчиков исключений в коде является то, что нельзя использовать **`goto`** оператор для перехода в блок инструкций **__try** . Входить в этот блок необходимо только через обычный поток управления. Можно выйти из блока инструкций **__try** и вложенных обработчиков исключений по мере выбора.

## <a name="see-also"></a>См. также статью

[Написание обработчика исключений](../cpp/writing-an-exception-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
