---
title: Ошибка компилятора C2583
ms.date: 11/04/2016
f1_keywords:
- C2583
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
ms.openlocfilehash: 0cb021dcba4d050afb943c03ba6b4dca053bcbb8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87206852"
---
# <a name="compiler-error-c2583"></a>Ошибка компилятора C2583

"идентификатор": недопустимый указатель "this" с модификатором const или volatile для конструкторов и деструкторов

Конструктор или деструктор объявлен **`const`** или **`volatile`** . Это не допускается.

Следующий пример приводит к возникновению ошибки C2583:

```cpp
// C2583.cpp
// compile with: /c
class A {
public:
   int i;
   A() const;   // C2583

   // try the following line instead
   // A();
};
```
