---
title: Ошибка компилятора C2723
ms.date: 11/04/2016
f1_keywords:
- C2723
helpviewer_keywords:
- C2723
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
ms.openlocfilehash: bc07a99f12ed0e447427990969e54f7f3d3d3b7f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383026"
---
# <a name="compiler-error-c2723"></a>Ошибка компилятора C2723

function: недопустимый описатель specifier в определении функции

Описатель не может использоваться в определении функции вне объявления класса. Описатель `virtual` может быть указан только в объявлении функции-члена внутри объявления класса.

В следующем примере показано возникновение ошибки C2723 и приводятся сведения по ее устранению.

```
// C2723.cpp
struct X {
   virtual void f();
   virtual void g();
};

virtual void X::f() {}   // C2723

// try the following line instead
void X::g() {}
```