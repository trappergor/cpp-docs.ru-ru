---
title: Ошибка компилятора C2391
ms.date: 11/04/2016
f1_keywords:
- C2391
helpviewer_keywords:
- C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
ms.openlocfilehash: 7683ad1580454bd7edb1fc08e5bd110a3e5c36c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62393627"
---
# <a name="compiler-error-c2391"></a>Ошибка компилятора C2391

«Идентификатор»: «friend» нельзя использовать во время определения типа

`friend` Объявление включает объявление полного класса. Объект `friend` можно указать в объявлении функции-члена или спецификаторе типа, но не объявление полного класса.

При компиляции следующего примера возникнет ошибка C2326:

```
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