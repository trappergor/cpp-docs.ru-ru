---
title: Ошибка компилятора C3828
ms.date: 11/04/2016
f1_keywords:
- C3828
helpviewer_keywords:
- C3828
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
ms.openlocfilehash: 68a82105a2ff7d58090e9f345bf7aafb34d492d4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515288"
---
# <a name="compiler-error-c3828"></a>Ошибка компилятора C3828

«Тип объекта»: аргументы размещения не разрешаются при создании экземпляров управляемых или WinRTclasses

При создании объекта управляемого типа или типа среды выполнения Windows, нельзя использовать формы размещения оператора [ref new, gcnew](../../windows/ref-new-gcnew-cpp-component-extensions.md) или [новый](../../cpp/new-operator-cpp.md).

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