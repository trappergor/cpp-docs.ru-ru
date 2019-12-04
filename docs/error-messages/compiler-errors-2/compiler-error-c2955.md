---
title: Ошибка компилятора C2955
ms.date: 03/28/2017
f1_keywords:
- C2955
helpviewer_keywords:
- C2955
ms.assetid: 77709fb6-d69b-46fd-a62f-e8564563d01b
ms.openlocfilehash: 8afdeaf43c0c9789753b9165f1e8a8287aaac76d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742877"
---
# <a name="compiler-error-c2955"></a>Ошибка компилятора C2955

identifier: для использования шаблона класса или универсального псевдонима требуется список аргументов шаблона или универсальный список аргументов

Шаблон класса или универсальный класс нельзя использовать в качестве идентификатора без списка аргументов шаблона или универсального списка аргументов.

Дополнительные сведения см. в разделе [шаблоны классов](../../cpp/class-templates.md).

В следующем примере показано возникновение ошибки C2955 и приводятся сведения по ее устранению.

```cpp
// C2955.cpp
// compile with: /c
template<class T>
class X {};

X x1;   // C2955
X<int> x2;   // OK - this is how to fix it.
```

Ошибка C2955 также может возникать при попытке определить вне строки функцию, объявленную в шаблоне класса:

```cpp
// C2955_b.cpp
// compile with: /c
template <class T>
class CT {
public:
   void CTFunc();
   void CTFunc2();
};

void CT::CTFunc() {}   // C2955

// OK - this is how to fix it
template <class T>
void CT<T>::CTFunc2() {}
```

Ошибка C2955 также может возникнуть при использовании универсальных шаблонов:

```cpp
// C2955_c.cpp
// compile with: /clr
generic <class T>
ref struct GC {
   T t;
};

int main() {
   GC^ g;   // C2955
   GC <int>^ g;
}
```

## <a name="example"></a>Пример

**Visual Studio 2017 и более поздние версии:** Компилятор правильно выполняет диагностику отсутствующих списков аргументов шаблона, когда шаблон появляется в списке параметров шаблона (например, в составе аргумента шаблона по умолчанию или в параметре шаблона, не являющемся типом). Следующий код компилируется в Visual Studio 2015, но выводит ошибку в Visual Studio 2017.

```
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```
