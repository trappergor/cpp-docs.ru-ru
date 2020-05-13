---
title: Предупреждение компилятора (уровень 1) C4508
ms.date: 11/04/2016
f1_keywords:
- C4508
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
ms.openlocfilehash: 54baf35eaeb5ef2c8add024f25c059480d60617b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186573"
---
# <a name="compiler-warning-level-1-c4508"></a>Предупреждение компилятора (уровень 1) C4508

"функция": функция должна возвращать значение; предполагается тип возвращаемого значения "void"

Для функции не указан тип возвращаемого значения. В этом случае следует также запустить C4430, и компилятор реализует исправление, сообщаемое C4430 (значение по умолчанию — int).

Чтобы устранить это предупреждение, явно объявите тип возвращаемого значения функций.

Следующий пример приводит к возникновению ошибки C4508:

```cpp
// C4508.cpp
// compile with: /W1 /c
#pragma warning (disable : 4430)
func() {}   // C4508
void func2() {}   // OK
```
