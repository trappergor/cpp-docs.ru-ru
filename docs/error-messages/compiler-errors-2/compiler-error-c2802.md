---
title: Ошибка компилятора C2802
ms.date: 11/04/2016
f1_keywords:
- C2802
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
ms.openlocfilehash: f872a4753907cd78c9118c22498777d5acc5b2fd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214585"
---
# <a name="compiler-error-c2802"></a>Ошибка компилятора C2802

статический член "operator оператор" не имеет формальных параметров

Оператор, объявленный **`static`** функцией-членом, должен иметь хотя бы один параметр.

Следующий пример приводит к возникновению ошибки C2802:

```cpp
// C2802.cpp
// compile with: /clr /c
ref class A {
   static operator+ ();   // C2802
   static operator+ (A^, A^);   // OK
};
```
