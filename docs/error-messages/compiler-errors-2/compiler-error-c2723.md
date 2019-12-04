---
title: Ошибка компилятора C2723
ms.date: 11/04/2016
f1_keywords:
- C2723
helpviewer_keywords:
- C2723
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
ms.openlocfilehash: f9b169f856dba7a76e5f67e1980c4ca47ba912de
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737456"
---
# <a name="compiler-error-c2723"></a>Ошибка компилятора C2723

function: недопустимый описатель specifier в определении функции

Описатель не может использоваться в определении функции вне объявления класса. Описатель `virtual` может быть указан только в объявлении функции-члена внутри объявления класса.

В следующем примере показано возникновение ошибки C2723 и приводятся сведения по ее устранению.

```cpp
// C2723.cpp
struct X {
   virtual void f();
   virtual void g();
};

virtual void X::f() {}   // C2723

// try the following line instead
void X::g() {}
```
