---
title: Ошибка компилятора C3181
ms.date: 11/04/2016
f1_keywords:
- C3181
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
ms.openlocfilehash: b37b28b4332b46aaaf803f58090a72c25e83f47f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587763"
---
# <a name="compiler-error-c3181"></a>Ошибка компилятора C3181

«Тип»: недопустимый операнд для оператора

Передан недопустимый параметр [typeid](../../windows/typeid-cpp-component-extensions.md) оператор. Параметр должен быть управляемым типом.

Обратите внимание на то, что компилятор использует псевдонимы для собственных типов, которые сопоставляются с типами в CLR.

Следующий пример приводит к возникновению ошибки C3181:

```
// C3181a.cpp
// compile with: /clr
using namespace System;

int main() {
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181
   Type ^pType2 = int::typeid;   // OK
}
```
