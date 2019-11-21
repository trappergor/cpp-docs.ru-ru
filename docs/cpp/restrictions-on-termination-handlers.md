---
title: Ограничения обработчиков завершения
ms.date: 11/04/2016
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
ms.openlocfilehash: 6c39407270037756c55dc42aed80e1d04616c9ee
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246383"
---
# <a name="restrictions-on-termination-handlers"></a>Ограничения обработчиков завершения

You cannot use a **goto** statement to jump into a **__try** statement block or a **__finally** statement block. Входить в этот блок необходимо только через обычный поток управления. (You can, however, jump out of a **__try** statement block.) Also, you cannot nest an exception handler or termination handler inside a **__finally** block.

Кроме того, некоторые типы кода, разрешенные в обработчике завершения, дают спорные результаты, поэтому их следует либо не использовать вообще, либо использовать с осторожностью. One is a **goto** statement that jumps out of a **__finally** statement block. Если блок выполняется как часть нормального завершения, ничего необычного не происходит. Однако если система разматывает стек, эта операция останавливается, и текущая функция получает контроль над происходящим, как если бы аномального завершения не было.

A **return** statement inside a **__finally** statement block presents roughly the same situation. Контроль возвращается непосредственному вызывающему объекту функции, которая содержит обработчик завершения. Если система разматывала стек, этот процесс останавливается, и программа выполняется, как если бы исключения не было создано.

## <a name="see-also"></a>См. также

[Writing a termination handler](../cpp/writing-a-termination-handler.md)<br/>
[Структурированная обработка исключений (C/C++)](../cpp/structured-exception-handling-c-cpp.md)