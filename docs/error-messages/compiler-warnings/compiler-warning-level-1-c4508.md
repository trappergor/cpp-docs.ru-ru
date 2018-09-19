---
title: Предупреждение компилятора (уровень 1) C4508 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4508
dev_langs:
- C++
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5abc1d81c3e94c02a63f73c84f3f5e5c7e9b0b0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038949"
---
# <a name="compiler-warning-level-1-c4508"></a>Предупреждение компилятора (уровень 1) C4508

«функция»: функция должна возвращать значение; «void» предполагается, что тип возвращаемого значения

Функция имеет не указан тип возвращаемого значения. В этом случае C4430 также должен срабатывать, и компилятор реализует исправление, о которых сообщает C4430 (значение по умолчанию — int).

Чтобы устранить это предупреждение, необходимо явно объявите тип возвращаемого значения функции.

Следующий пример приводит к возникновению ошибки C4508:

```
// C4508.cpp
// compile with: /W1 /c
#pragma warning (disable : 4430)
func() {}   // C4508
void func2() {}   // OK
```