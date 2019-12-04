---
title: Ошибка компилятора C3634
ms.date: 11/04/2016
f1_keywords:
- C3634
helpviewer_keywords:
- C3634
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
ms.openlocfilehash: 2abf5191035e450dca72777cdc2b2675ac9b90de
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742591"
---
# <a name="compiler-error-c3634"></a>Ошибка компилятора C3634

"функция": невозможно определить абстрактный метод управляемого или Винрткласс

Абстрактный метод может быть объявлен в управляемом классе или классе WinRT, но он не может быть определен.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3634:

```cpp
// C3634.cpp
// compile with: /clr
ref class C {
   virtual void f() = 0;
};

void C::f() {   // C3634 - don't define managed class' pure virtual method
}
```
