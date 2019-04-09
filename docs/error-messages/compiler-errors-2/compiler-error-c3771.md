---
title: Ошибка компилятора C3771
ms.date: 11/04/2016
f1_keywords:
- C3771
helpviewer_keywords:
- C3771
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
ms.openlocfilehash: 6b15d867bbaf66f511cbda200d692f5db4371ab3
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59026711"
---
# <a name="compiler-error-c3771"></a>Ошибка компилятора C3771

"идентификатор": в ближайшей области пространства имен не удалось найти дружественное объявление

Объявление шаблона класса для указанного шаблона *идентификатор* не удалось найти в текущем пространстве имен.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Убедитесь, что объявление шаблона класса для идентификатора шаблона задается в текущем пространстве имен или что идентификатор шаблона является полным именем.

## <a name="example"></a>Пример

Следующий пример кода объявляет шаблон класса и функцию в пространстве имен `NA`, но пытается объявить шаблон дружественной функции в пространстве имен `NB`.

```cpp
// C3771.cpp
// compile with: /c

namespace NA {
template<class T> class A {
    void aFunction(T t) {};
    };
}
// using namespace NA;
namespace NB {
    class X {
        template<class T> friend void A<T>::aFunction(T); // C3771
// try the following line instead
//      template<class T> friend void NA::A<T>::aFunction(T);
// or try "using namespace NA;" instead.
    };
}
```

## <a name="see-also"></a>См. также

[Шаблоны](../../cpp/templates-cpp.md)