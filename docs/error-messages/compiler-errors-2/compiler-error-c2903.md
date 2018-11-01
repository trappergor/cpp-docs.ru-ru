---
title: Ошибка компилятора C2903
ms.date: 11/04/2016
f1_keywords:
- C2903
helpviewer_keywords:
- C2903
ms.assetid: bf6b223f-4921-48c7-82b9-ff318b42c801
ms.openlocfilehash: 7002e45770c994d5cd10e1cd632561be57246086
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442826"
---
# <a name="compiler-error-c2903"></a>Ошибка компилятора C2903

"идентификатор: символ не является ни шаблоном класса, ни шаблоном функции

Код пытается явно создать экземпляр объекта, который не является шаблоном.

В следующем примере возникает ошибка C2903:

```
// C2903.cpp
// compile with: /c
namespace N {
   template<class T> class X {};
   class Y {};
}
void g() {
   N::template Y y;   // C2903
   N::X<N::Y> y;   // OK
}
```

Ошибка C2903 также может возникнуть при использовании универсальных шаблонов:

```
// C2903b.cpp
// compile with: /clr /c
namespace N {
   class Y {};
   generic<class T> ref class Z {};
}

void f() {
   N::generic Y y;   // C2903
   N:: generic Z<int>^ z;   // OK
}
```