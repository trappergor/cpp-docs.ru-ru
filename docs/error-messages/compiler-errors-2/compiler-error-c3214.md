---
title: Ошибка компилятора C3214
ms.date: 11/04/2016
f1_keywords:
- C3214
helpviewer_keywords:
- C3214
ms.assetid: 49ee4a9a-2549-4adb-9d3a-38e154303c2e
ms.openlocfilehash: e4f271ec4abdc05b5cf148e40a752b4d62cc884c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182552"
---
# <a name="compiler-error-c3214"></a>Ошибка компилятора C3214

"тип": недопустимый аргумент типа для универсального параметра "param" универсального типа "универсальный_тип", не соответствует ограничению "ограничение"

Для создания экземпляра универсального класса указан тип, который не соответствует ограничению универсального класса.

Следующий пример приводит к возникновению ошибки C3214:

```
// C3214.cpp
// compile with: /clr
interface struct A {};

generic <class T>
where T : A
ref class C {};

ref class X : public A {};

int main() {
   C<int>^ c = new C<int>;   // C3214
   C<X ^> ^ c2 = new C<X^>;   // OK
}
```