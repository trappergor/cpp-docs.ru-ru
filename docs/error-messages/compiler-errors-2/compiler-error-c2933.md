---
title: Ошибка компилятора C2933
ms.date: 11/04/2016
f1_keywords:
- C2933
helpviewer_keywords:
- C2933
ms.assetid: 394891e3-6b52-4b61-83d2-a1c5125d9bd5
ms.openlocfilehash: 8764ce7f79243eec931904378522b90a41b633a7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512597"
---
# <a name="compiler-error-c2933"></a>Ошибка компилятора C2933

"класс": идентификатор класса типа переопределен как член typedef "идентификатор"

Универсальный класс или класс-шаблон нельзя использовать в качестве члена `typedef` .

Следующий пример приводит к возникновению ошибки C2933:

```
// C2933.cpp
// compile with: /c
template<class T> struct TC { };
struct MyStruct {
   typedef int TC<int>;   // C2933
};

struct TC2 { };
struct MyStruct2 {
   typedef int TC2;
};
```

Ошибка C2933 также может возникнуть при использовании универсальных шаблонов.

```
// C2933b.cpp
// compile with: /clr /c
generic<class T> ref struct GC { };
struct MyStruct {
   typedef int GC<int>;   // C2933
};

ref struct GC2 { };
struct MyStruct2 {
   typedef int GC2;
};
```