---
title: Ошибка компилятора C2391
ms.date: 11/04/2016
f1_keywords:
- C2391
helpviewer_keywords:
- C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
ms.openlocfilehash: f000287c5934a39d56342bce0f6c9ca2c69e2297
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212739"
---
# <a name="compiler-error-c2391"></a>Ошибка компилятора C2391

"идентификатор": "Friend" не может использоваться во время определения типа

**`friend`** Объявление содержит полное объявление класса. **`friend`** Объявление может указывать функцию-член или настраиваемый спецификатор типа, но не полное объявление класса.

При компиляции следующего примера возникнет ошибка C2326:

```cpp
// C2391.cpp
// compile with: /c
class D {
   void func( int );
};

class A {
   friend class B { int i; };   // C2391

   // OK
   friend class C;
   friend void D::func(int);
};
```
