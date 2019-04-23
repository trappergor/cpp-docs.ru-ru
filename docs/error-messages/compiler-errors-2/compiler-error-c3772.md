---
title: Ошибка компилятора C3772
ms.date: 11/04/2016
f1_keywords:
- C3772
helpviewer_keywords:
- C3772
ms.assetid: 63e938d4-088d-41cc-a562-5881a05b5710
ms.openlocfilehash: 420e1eb12cbb178459a96f55efab444a538e6c2b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027940"
---
# <a name="compiler-error-c3772"></a>Ошибка компилятора C3772

"имя": недопустимое объявление дружественного шаблона

Не допускается объявлять дружественный элемент для специализации шаблона класса. Вы не можете объявить в одном операторе явную или частичную специализацию шаблона класса и дружественный элемент для этой специализации. *Имя* идентифицирует недопустимое объявление.

### <a name="to-correct-this-error"></a>Исправление ошибки

- Не объявляйте дружественный элемент для специализации шаблона класса.

- Если это нужно в вашем приложении, объявите дружественный элемент для шаблона класса либо для конкретной частичной или явной специализации.

## <a name="example"></a>Пример

В следующем примере кода произойдет ошибка компиляции из-за объявления дружественного элемента для частичной специализации шаблона класса.

```cpp
// c3772.cpp
// compile with: /c

// A class template.
    template<class T> class A {};

// A partial specialization of the class template.
    template<class T> class A<T*> {};

// An explicit specialization.
    template<> class A<char>;

class X {
// Invalid declaration of a friend of a partial specialization.
    template<class T> friend class A<T*>; // C3772

// Instead, if it is appropriate for your application, declare a
// friend of the class template. Consequently, all specializations
// of the class template are friends:
//    template<class T> friend class A;
// Or declare a friend of a particular partial specialization:
//    friend class A<int*>;
// Or declare a friend of a particular explicit specialization:
//    friend class A<char>;
};
```

## <a name="see-also"></a>См. также

[Шаблоны](../../cpp/templates-cpp.md)<br/>
[Специализация шаблонов](../../cpp/template-specialization-cpp.md)
