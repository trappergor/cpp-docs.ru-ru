---
title: Ошибка компилятора C2937
ms.date: 11/04/2016
f1_keywords:
- C2937
helpviewer_keywords:
- C2937
ms.assetid: 95671ca3-79f7-4b56-a5f2-a92296da1629
ms.openlocfilehash: 615b4fbb639249179d34f0d92b4891aadc0ff3a8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233409"
---
# <a name="compiler-error-c2937"></a>Ошибка компилятора C2937

"класс": идентификатор класса типа переопределен как глобальное определение типа (typedef)

Универсальный шаблон или класс шаблона нельзя использовать в качестве глобального **`typedef`** .

Следующий пример приводит к возникновению ошибки C2937:

```cpp
// C2937.cpp
// compile with: /c
template<class T>
struct TC { };
typedef int TC<int>;   // C2937
typedef TC<int> c;   // OK
```

Ошибка C2937 также может возникнуть при использовании универсальных шаблонов.

```cpp
// C2937b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };
typedef int GC<int>;   // C2937
typedef GC<int> xx;   // OK
```
