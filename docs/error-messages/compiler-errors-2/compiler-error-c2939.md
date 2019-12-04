---
title: Ошибка компилятора C2939
ms.date: 11/04/2016
f1_keywords:
- C2939
helpviewer_keywords:
- C2939
ms.assetid: 455b050b-f2dc-4b5b-bd6a-e1f81d3d1644
ms.openlocfilehash: 97aa24eccb5cec7d74f7f7660260fa8b5f6d8d7d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754619"
---
# <a name="compiler-error-c2939"></a>Ошибка компилятора C2939

"класс": идентификатор класса типа переопределен как локальная переменная данных

Универсальный класс или класс шаблона нельзя использовать в качестве локальной переменной данных.

Эта ошибка может возникнуть при неправильной расстановке скобок.

В следующем примере возникает ошибка C2939:

```cpp
// C2939.cpp
template<class T>
struct TC { };
int main() {
   int TC<int>;   // C2939
   int TC;   // OK
}
```

Ошибка C2939 также может возникнуть при использовании универсальных шаблонов:

```cpp
// C2939b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };

int main() {
   int GC<int>;   // C2939
   int GC;   // OK
}
```
