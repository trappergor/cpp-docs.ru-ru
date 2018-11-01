---
title: Ошибка компилятора C2534
ms.date: 11/04/2016
f1_keywords:
- C2534
helpviewer_keywords:
- C2534
ms.assetid: 481f9f54-5b51-4aa0-8eea-218f10807705
ms.openlocfilehash: e684804ea31b16f31c82e244cb4f9a6aaf2d08c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638260"
---
# <a name="compiler-error-c2534"></a>Ошибка компилятора C2534

«Идентификатор»: конструктор не может возвращать значение

Конструктор не может возвращать значение или иметь тип возвращаемого значения (даже `void` тип возвращаемого значения).

Чтобы устранить эту ошибку, удалив `return` оператора из определения конструктора.

Следующий пример приводит к возникновению ошибки C2534:

```
// C2534.cpp
class A {
public:
   int i;
   A() { return i; }   // C2534
};
```