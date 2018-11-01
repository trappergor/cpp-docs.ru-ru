---
title: Ошибка компилятора C2937
ms.date: 11/04/2016
f1_keywords:
- C2937
helpviewer_keywords:
- C2937
ms.assetid: 95671ca3-79f7-4b56-a5f2-a92296da1629
ms.openlocfilehash: 8ad25dbcec4ee8a8ed49449cf9e64ebae4af1321
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541015"
---
# <a name="compiler-error-c2937"></a>Ошибка компилятора C2937

"класс": идентификатор класса типа переопределен как глобальное определение типа (typedef)

Универсальный класс или класс шаблона нельзя использовать в качестве глобального `typedef`.

Следующий пример приводит к возникновению ошибки C2937:

```
// C2937.cpp
// compile with: /c
template<class T>
struct TC { };
typedef int TC<int>;   // C2937
typedef TC<int> c;   // OK
```

Ошибка C2937 также может возникнуть при использовании универсальных шаблонов.

```
// C2937b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };
typedef int GC<int>;   // C2937
typedef GC<int> xx;   // OK
```