---
title: Ошибка компилятора C3828
ms.date: 11/04/2016
f1_keywords:
- C3828
helpviewer_keywords:
- C3828
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
ms.openlocfilehash: f499bb2a8fd6d3148935daec89835b79d2ff5b49
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58770555"
---
# <a name="compiler-error-c3828"></a>Ошибка компилятора C3828

«Тип объекта»: аргументы размещения не разрешаются при создании экземпляров управляемых или WinRTclasses

При создании объекта управляемого типа или типа среды выполнения Windows, нельзя использовать формы размещения оператора [ref new, gcnew](../../extensions/ref-new-gcnew-cpp-component-extensions.md) или [новый](../../cpp/new-operator-cpp.md).

В следующем примере показано возникновение ошибки C3828 и приводятся сведения по ее устранению.

```
// C3828a.cpp
// compile with: /clr
ref struct M {
};

ref struct N {
   static array<char>^ bytes = gcnew array<char>(256);
};

int main() {
   M ^m1 = new (&N::bytes) M();   // C3828
   // The following line fixes the error.
   // M ^m1 = gcnew M();
}
```