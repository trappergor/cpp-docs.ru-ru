---
title: Ошибка компилятора C3842
ms.date: 11/04/2016
f1_keywords:
- C3842
helpviewer_keywords:
- C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
ms.openlocfilehash: a61a69aca53f7f8996d0261a57b749930ecc01cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385515"
---
# <a name="compiler-error-c3842"></a>Ошибка компилятора C3842

function: квалификаторы const и volatile для функций-членов управляемых типов или типов WinRT не поддерживаются

[const](../../cpp/const-cpp.md) и [volatile](../../cpp/volatile-cpp.md) не поддерживаются для функций-членов управляемых типов или типов среды выполнения Windows.

Следующий пример приводит к возникновению ошибки C3842:

```
// C3842a.cpp
// compile with: /clr /c
public ref struct A {
   void f() const {}   // C3842
   void f() volatile {}   // C3842

   void f() {}
};
```