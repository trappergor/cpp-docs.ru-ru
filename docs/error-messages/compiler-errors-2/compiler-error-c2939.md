---
title: Ошибка компилятора C2939
ms.date: 11/04/2016
f1_keywords:
- C2939
helpviewer_keywords:
- C2939
ms.assetid: 455b050b-f2dc-4b5b-bd6a-e1f81d3d1644
ms.openlocfilehash: 59b2f63ba12a644f13b3586fbf6eec4d5bfa8be5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302661"
---
# <a name="compiler-error-c2939"></a>Ошибка компилятора C2939

"класс": идентификатор класса типа переопределен как локальная переменная данных

Универсальный класс или класс шаблона нельзя использовать в качестве локальной переменной данных.

Эта ошибка может возникнуть при неправильной расстановке скобок.

В следующем примере возникает ошибка C2939:

```
// C2939.cpp
template<class T>
struct TC { };
int main() {
   int TC<int>;   // C2939
   int TC;   // OK
}
```

Ошибка C2939 также может возникнуть при использовании универсальных шаблонов:

```
// C2939b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };

int main() {
   int GC<int>;   // C2939
   int GC;   // OK
}
```