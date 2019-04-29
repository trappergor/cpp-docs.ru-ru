---
title: Ошибка компилятора C3269
ms.date: 11/04/2016
f1_keywords:
- C3269
helpviewer_keywords:
- C3269
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
ms.openlocfilehash: 406b388460b3d449471c884dd6461f2ce59a10f6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62365719"
---
# <a name="compiler-error-c3269"></a>Ошибка компилятора C3269

«функция»: функция член управляемого или WinRTtype не может объявляться с помощью «...»

Функции-члены управляемого класса и класса WinRT не могут объявлять списки параметров переменной длины.

В следующем примере показано возникновение ошибки C3269 и приводятся сведения по ее устранению.

```
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
