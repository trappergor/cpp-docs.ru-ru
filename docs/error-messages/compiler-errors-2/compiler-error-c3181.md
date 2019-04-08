---
title: Ошибка компилятора C3181
ms.date: 11/04/2016
f1_keywords:
- C3181
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
ms.openlocfilehash: dc848d4108ed4a1a7b6646647a1bbb1ec8dcadf7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781813"
---
# <a name="compiler-error-c3181"></a>Ошибка компилятора C3181

«Тип»: недопустимый операнд для оператора

Передан недопустимый параметр [typeid](../../extensions/typeid-cpp-component-extensions.md) оператор. Параметр должен быть управляемым типом.

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
