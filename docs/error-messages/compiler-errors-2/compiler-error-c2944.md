---
title: Ошибка компилятора C2944 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2944
dev_langs:
- C++
helpviewer_keywords:
- C2944
ms.assetid: f209e668-e72f-442a-a438-8c4ff43a404a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be9052ddc42c2f13e971c8655ac3382e3e1c89a7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083084"
---
# <a name="compiler-error-c2944"></a>Ошибка компилятора C2944

"класс": идентификатор типа класса переопределен как аргумент значения шаблона

Нельзя использовать универсальный класс или класс шаблона в качестве аргумента значения шаблона вместо символа.

В следующем примере возникает ошибка C2944:

```
// C2944.cpp
// compile with: /c
template<class T>
class TC { };

template <int TC<int> > struct X1 { };   // C2944

template <class T > struct X2 {};
```

Ошибка C2944 также может возникнуть при использовании универсальных шаблонов:

```
// C2944b.cpp
// compile with: /clr /c
generic<class T>
ref class GC {};

template <int GC<int> > struct X2 { };   // C2944
template <class T> struct X3 {};   // OK
```