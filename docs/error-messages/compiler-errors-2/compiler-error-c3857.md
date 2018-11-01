---
title: Ошибка компилятора C3857
ms.date: 11/04/2016
f1_keywords:
- C3857
helpviewer_keywords:
- C3857
ms.assetid: 9f746d1e-9708-4945-bc29-3150d5371d3c
ms.openlocfilehash: 1270d09c870bfdf9f390d6afb1625ad3e99e01a0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456892"
---
# <a name="compiler-error-c3857"></a>Ошибка компилятора C3857

«Тип»: несколько списков параметров типа не допускаются.

Больше одного шаблона или универсального был указан для одного типа, что не допускается.

В следующем примере возникает ошибка C3857:

```
// C3857.cpp
template <class T, class TT>
template <class T2>    // C3857
struct B {};
```

Возможное решение

```
// C3857b.cpp
// compile with: /c
template <class T, class TT, class T2>
struct B {};
```

C3857 также может возникнуть при использовании универсальных шаблонов:

```
// C3857c.cpp
// compile with: /clr
generic <typename T>
generic <typename U>
ref class GC;   // C3857
```

Возможное решение

```
// C3857d.cpp
// compile with: /clr /c
generic <typename U>
ref class GC;
```