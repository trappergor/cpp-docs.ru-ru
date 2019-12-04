---
title: Ошибка компилятора C3181
ms.date: 11/04/2016
f1_keywords:
- C3181
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
ms.openlocfilehash: e30ed7016ca3a4d4948a08c5c09268e52c9a407d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761677"
---
# <a name="compiler-error-c3181"></a>Ошибка компилятора C3181

"тип": недопустимый операнд для оператора

Оператору [typeid](../../extensions/typeid-cpp-component-extensions.md) передан недопустимый параметр. Параметр должен быть управляемым типом.

Обратите внимание, что компилятор использует Псевдонимы для собственных типов, которые сопоставляются с типами в среде CLR.

Следующий пример приводит к возникновению ошибки C3181:

```cpp
// C3181a.cpp
// compile with: /clr
using namespace System;

int main() {
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181
   Type ^pType2 = int::typeid;   // OK
}
```
