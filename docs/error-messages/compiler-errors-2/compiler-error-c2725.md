---
title: Ошибка компилятора C2725
ms.date: 11/04/2016
f1_keywords:
- C2725
helpviewer_keywords:
- C2725
ms.assetid: 13cd5b1b-e906-4cd8-9b2b-510d587c665a
ms.openlocfilehash: b2e8c6a2d3368e2f7fc1277e3bf727848da50881
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90741401"
---
# <a name="compiler-error-c2725"></a>Ошибка компилятора C2725

exception: невозможно выдать или перехватить управляемый объект или объект WinRT по значению или ссылке

Тип управляемого исключения или исключения WinRT неправилен.

## <a name="examples"></a>Примеры

В следующем примере показано возникновение ошибки C2725 и приводятся сведения по ее устранению.

```cpp
// C2725.cpp
// compile with: /clr
ref class R {
public:
   int i;
};

int main() {
   R % r1 = *gcnew R;
   throw r1;   // C2725

   R ^ r2 = gcnew R;
   throw r2;   // OK
}
```

В следующем примере показано возникновение ошибки C2725 и приводятся сведения по ее устранению.

```cpp
// C2725b.cpp
// compile with: /clr
using namespace System;
int main() {
   try {}
   catch( System::Exception%) {}   // C2725
   // try the following line instead
   // catch( System::Exception ^e) {}
}
```
