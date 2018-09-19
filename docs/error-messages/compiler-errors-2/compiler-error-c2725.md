---
title: Ошибка компилятора C2725 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2725
dev_langs:
- C++
helpviewer_keywords:
- C2725
ms.assetid: 13cd5b1b-e906-4cd8-9b2b-510d587c665a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 969ddd9343073dff3732204eb4b17375bb5ab9cc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056044"
---
# <a name="compiler-error-c2725"></a>Ошибка компилятора C2725

exception: невозможно выдать или перехватить управляемый объект или объект WinRT по значению или ссылке

Тип управляемого исключения или исключения WinRT неправилен.

## <a name="example"></a>Пример

В следующем примере показано возникновение ошибки C2725 и приводятся сведения по ее устранению.

```
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

## <a name="example"></a>Пример

В следующем примере показано возникновение ошибки C2725 и приводятся сведения по ее устранению.

```
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
