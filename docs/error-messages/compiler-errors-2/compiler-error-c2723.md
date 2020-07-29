---
title: Ошибка компилятора C2723
ms.date: 11/04/2016
f1_keywords:
- C2723
helpviewer_keywords:
- C2723
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
ms.openlocfilehash: f723fcc0a3d9626f01f2059a3d9363801221bca0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216054"
---
# <a name="compiler-error-c2723"></a>Ошибка компилятора C2723

function: недопустимый описатель specifier в определении функции

Описатель не может использоваться в определении функции вне объявления класса. **`virtual`** Спецификатор может быть указан только в объявлении функции-члена в объявлении класса.

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
