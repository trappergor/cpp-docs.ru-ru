---
title: Ошибка компилятора C2762
ms.date: 11/04/2016
f1_keywords:
- C2762
helpviewer_keywords:
- C2762
ms.assetid: 8b81a801-fd48-40a1-8bee-0748795b12e4
ms.openlocfilehash: c2f325fc9266321f224429afd3c295141627ecd6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759858"
---
# <a name="compiler-error-c2762"></a>Ошибка компилятора C2762

"класс": недопустимое выражение в качестве аргумента шаблона для "Argument"

При использовании [/Za](../../build/reference/za-ze-disable-language-extensions.md)компилятор не будет преобразовывать целочисленный объект в указатель.

Следующий пример приводит к возникновению ошибки C2762:

```cpp
// C2762.cpp
// compile with: /Za
template<typename T, T *pT>
class X2 {};

void f2() {
   X2<int, 0> x21;   // C2762
   // try the following line instead
   // X2<int, static_cast<int *>(0)> x22;
}
```
