---
title: Ошибка компилятора C2936
ms.date: 11/04/2016
f1_keywords:
- C2936
helpviewer_keywords:
- C2936
ms.assetid: 5d1ba0fc-0c78-4a37-a83b-1ef8527763be
ms.openlocfilehash: 547690302661656cc5368f5969432de68ac91e3f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539559"
---
# <a name="compiler-error-c2936"></a>Ошибка компилятора C2936

"класс": идентификатор класса типа переопределен как глобальная переменная данных

Универсальный класс или класс шаблона нельзя использовать в качестве глобальной переменной данных.

Эта ошибка может возникнуть при неправильной расстановке скобок.

Следующий пример приводит к возникновению ошибки C2936:

```
// C2936.cpp
// compile with: /c
template<class T> struct TC { };
int TC<int>;   // C2936

// OK
struct TC2 { };
int TC2;
```

Ошибка C2936 также может возникнуть при использовании универсальных шаблонов:

```
// C2936b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};
int GC<int>;   // C2936

// OK
ref struct GC2 {};
int GC2;
```