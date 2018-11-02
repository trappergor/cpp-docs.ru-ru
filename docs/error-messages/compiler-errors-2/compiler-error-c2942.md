---
title: Ошибка компилятора C2942
ms.date: 11/04/2016
f1_keywords:
- C2942
helpviewer_keywords:
- C2942
ms.assetid: 13abf744-8fa1-450d-886d-e5717c04956e
ms.openlocfilehash: 8a594b9d1d8374caa972f6bfdafe5d691e634a9a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632574"
---
# <a name="compiler-error-c2942"></a>Ошибка компилятора C2942

"класс": идентификатор класса типа переопределен как формальный аргумент функции

Универсальный класс или класс-шаблон нельзя использовать в качестве формального аргумента. Аргумент нельзя передать прямо в конструктор универсального класса или класса-шаблона.

Следующий пример приводит к возникновению ошибки C2942:

```

// C2942.cpp
// compile with: /c
template<class T>
struct TC {};
void f(int TC<int>) {}   // C2942

// OK
struct TC2 {};
void f(TC2 i) {}
```

Ошибка C2942 также может возникнуть при использовании универсальных шаблонов:

```
// C2942b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC {};
void f(int GC<int>) {}   // C2942
ref struct GC2 { };
void f(int GC2) {}
```