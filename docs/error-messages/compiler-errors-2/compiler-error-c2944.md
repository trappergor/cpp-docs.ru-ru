---
title: Ошибка компилятора C2944
ms.date: 11/04/2016
f1_keywords:
- C2944
helpviewer_keywords:
- C2944
ms.assetid: f209e668-e72f-442a-a438-8c4ff43a404a
ms.openlocfilehash: 542f7def550632a29fcb7ae28825b32b8c26f17d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755386"
---
# <a name="compiler-error-c2944"></a>Ошибка компилятора C2944

"класс": идентификатор типа класса переопределен как аргумент значения шаблона

Нельзя использовать универсальный класс или класс шаблона в качестве аргумента значения шаблона вместо символа.

В следующем примере возникает ошибка C2944:

```cpp
// C2944.cpp
// compile with: /c
template<class T>
class TC { };

template <int TC<int> > struct X1 { };   // C2944

template <class T > struct X2 {};
```

Ошибка C2944 также может возникнуть при использовании универсальных шаблонов:

```cpp
// C2944b.cpp
// compile with: /clr /c
generic<class T>
ref class GC {};

template <int GC<int> > struct X2 { };   // C2944
template <class T> struct X3 {};   // OK
```
