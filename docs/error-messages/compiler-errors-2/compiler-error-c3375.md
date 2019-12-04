---
title: Ошибка компилятора C3375
ms.date: 11/04/2016
f1_keywords:
- C3375
helpviewer_keywords:
- C3375
ms.assetid: f1df78c6-e6ca-48f3-8b29-4e1710002bf3
ms.openlocfilehash: cf92f0fabecfa7292a4d6a8644746c489cbf139f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759754"
---
# <a name="compiler-error-c3375"></a>Ошибка компилятора C3375

"функция": неоднозначная функция делегата

Создание экземпляра делегата могло быть выполнено в статической функции-члене или как непривязанного делегата для функции экземпляра, поэтому компилятор выдал данную ошибку.

Дополнительные сведения см. в разделе [DelegateC++ (расширения компонентов)](../../extensions/delegate-cpp-component-extensions.md).

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3375:

```cpp
// C3375.cpp
// compile with: /clr
ref struct R {
   static void f(R^) {}
   void f() {}
};

delegate void Del(R^);

int main() {
   Del ^ a = gcnew Del(&R::f);   // C3375
}
```
