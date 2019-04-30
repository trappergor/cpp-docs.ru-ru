---
title: Ограничения обработчиков исключений
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 7d5bf20da61f4b9f5012b7f2aab932dfc904c302
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403364"
---
# <a name="restrictions-on-exception-handlers"></a>Ограничения обработчиков исключений

Главное ограничение на использование обработчиков исключений в коде в том, что нельзя использовать **goto** инструкцию, чтобы перейти к **__try** блока инструкций. Входить в этот блок необходимо только через обычный поток управления. Вы можете переходить из **__try** инструкции блокировать и создавать вложенные обработчики исключений, как захотите.

## <a name="see-also"></a>См. также

[Написание обработчика исключений](../cpp/writing-an-exception-handler.md)<br/>
[Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)