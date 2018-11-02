---
title: Ошибка компилятора C3182
ms.date: 11/04/2016
f1_keywords:
- C3182
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
ms.openlocfilehash: 6866c7bbcee0a4097e490b344c79a6eec7f94570
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626750"
---
# <a name="compiler-error-c3182"></a>Ошибка компилятора C3182

«класс»: член объявление using или объявление доступа не допускается без управляемого или WinRTtype

Объект [с помощью](../../cpp/using-declaration.md) объявление недопустимо во всех формах управляемых классов.

В следующем примере показано возникновение ошибки C3182 и приводятся сведения по ее устранению.

```
// C3182a.cpp
// compile with: /clr /c
ref struct B {
   void mf(int) {
   }
};

ref struct D : B {
   using B::mf;   // C3182, delete to resolve
   void mf(char) {
   }
};
```
