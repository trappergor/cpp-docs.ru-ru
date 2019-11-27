---
title: Ограничения, действующие в отношении обработчиков исключений
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 030d444443b3a6e3e2e0ac0e015619046a76d562
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245147"
---
# <a name="restrictions-on-exception-handlers"></a>Ограничения, действующие в отношении обработчиков исключений

Основным ограничением использования обработчиков исключений в коде является то, что нельзя использовать оператор **goto** для перехода в блок инструкций **__try** . Входить в этот блок необходимо только через обычный поток управления. Можно выйти из блока инструкций **__try** и вложенных обработчиков исключений по мере выбора.

## <a name="see-also"></a>См. также:

[Написание обработчика исключений](../cpp/writing-an-exception-handler.md)<br/>
[Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)