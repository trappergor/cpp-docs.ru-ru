---
title: Ошибка компилятора C3609
ms.date: 11/04/2016
f1_keywords:
- C3609
helpviewer_keywords:
- C3609
ms.assetid: 801e7f79-4ac6-4f8f-955f-703cdf095d00
ms.openlocfilehash: 1d3078614ff6818dd4185b3bd5ed2f49413db16f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755958"
---
# <a name="compiler-error-c3609"></a>Ошибка компилятора C3609

member: запечатанная или окончательная функция должна быть виртуальной

[Запечатанные](../../extensions/sealed-cpp-component-extensions.md) и [окончательные](../../cpp/final-specifier.md) ключевые слова разрешены только для класса, структуры или функции-члена, помеченной `virtual`.

Следующий пример приводит к возникновению ошибки C3609:

```cpp
// C3609.cpp
// compile with: /clr /c
ref class C {
   int f() sealed;   // C3609
   virtual int f2() sealed;   // OK
};
```
