---
title: Ошибка компилятора C3828 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3828
dev_langs:
- C++
helpviewer_keywords:
- C3828
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f91a4a414a881aced6e537c0b98e69896aeeb4c3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085489"
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