---
title: Ошибка компилятора C3214
ms.date: 11/04/2016
f1_keywords:
- C3214
helpviewer_keywords:
- C3214
ms.assetid: 49ee4a9a-2549-4adb-9d3a-38e154303c2e
ms.openlocfilehash: 4eda0abd0bbfb3bf5757e39062fa3c229f698624
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756192"
---
# <a name="compiler-error-c3214"></a>Ошибка компилятора C3214

"тип": недопустимый аргумент типа для универсального параметра "param" универсального типа "универсальный_тип", не соответствует ограничению "ограничение"

Для создания экземпляра универсального класса указан тип, который не соответствует ограничению универсального класса.

Следующий пример приводит к возникновению ошибки C3214:

```cpp
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
