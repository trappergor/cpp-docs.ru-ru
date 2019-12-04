---
title: Ошибка компилятора C3269
ms.date: 11/04/2016
f1_keywords:
- C3269
helpviewer_keywords:
- C3269
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
ms.openlocfilehash: 95f71c9312faaf5c14bd8990898257002c528c0e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754021"
---
# <a name="compiler-error-c3269"></a>Ошибка компилятора C3269

"функция": невозможно объявить функцию-член управляемого или Винрттипе с "..."

Функции-члены управляемого класса и класса WinRT не могут объявлять списки параметров переменной длины.

В следующем примере показано возникновение ошибки C3269 и приводятся сведения по ее устранению.

```cpp
// C3269_2.cpp
// compile with: /clr

ref struct A
{
   void func(int i, ...)   // C3269
   // try the following line instead
   // void func(int i )
   {
   }
};

int main()
{
}
```
