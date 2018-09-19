---
title: Ошибка компилятора C2955 | Документация Майкрософт
ms.custom: ''
ms.date: 03/28/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2955
dev_langs:
- C++
helpviewer_keywords:
- C2955
ms.assetid: 77709fb6-d69b-46fd-a62f-e8564563d01b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c9d9817a2b78638868242c5c5642a89fb41d93c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051949"
---
# <a name="compiler-error-c2955"></a>Ошибка компилятора C2955

identifier: для использования шаблона класса или универсального псевдонима требуется список аргументов шаблона или универсальный список аргументов

Шаблон класса или универсальный класс нельзя использовать в качестве идентификатора без списка аргументов шаблона или универсального списка аргументов.

Дополнительные сведения см. в разделе [шаблонов классов](../../cpp/class-templates.md).

В следующем примере показано возникновение ошибки C2955 и приводятся сведения по ее устранению.

```
// C2955.cpp
// compile with: /c
template<class T>
class X {};

X x1;   // C2955
X<int> x2;   // OK - this is how to fix it.
```

Ошибка C2955 также может возникать при попытке определить вне строки функцию, объявленную в шаблоне класса:

```
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

```
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

**Visual Studio 2017 и более поздних версий:** компилятор правильно диагностирует отсутствующие списки аргументов шаблона, когда шаблон появится в списке параметров шаблона (например, как часть аргумента шаблона по умолчанию или параметр шаблона, не являющийся типом). Следующий код компилируется в Visual Studio 2015, но выводит ошибку в Visual Studio 2017.

```
template <class T> class ListNode;
template <class T> using ListNodeMember = ListNode<T> T::*;
template <class T, ListNodeMember M> class ListHead; // C2955: 'ListNodeMember': use of alias
                                                     // template requires template argument list

// correct:  template <class T, ListNodeMember<T> M> class ListHead;
```
