---
title: Ошибка компилятора C2881
ms.date: 11/04/2016
f1_keywords:
- C2881
helpviewer_keywords:
- C2881
ms.assetid: b49c63c2-b064-4d4b-a75e-ddd2af947522
ms.openlocfilehash: 82a4fbe94bc7250244d57f549e52037d6a54c784
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62378920"
---
# <a name="compiler-error-c2881"></a>Ошибка компилятора C2881

пространство имен «1»: уже используется в качестве псевдонима для пространства имен «2»

Тем же именем невозможно использовать в качестве псевдонима для двух пространств имен.

Следующий пример приводит к возникновению ошибки C2881:

```
// C2881.cpp
// compile with: /c
namespace A {
   int k;
}

namespace B {
   int i;
}

namespace C = A;
namespace C = B;   // C2881 C is already an alias for A
```