---
title: Класс add_cv
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_cv
helpviewer_keywords:
- add_cv class
- add_cv
ms.assetid: a5572c78-a097-45d7-b476-ed4876889dea
ms.openlocfilehash: 412dc8426112e65d00b572a65f064667d2709a0d
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620783"
---
# <a name="add_cv-class"></a>Класс add_cv

Делает тип **const volatile независимым** от типа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct add_cv;

template <class T>
using add_cv_t = typename add_cv<T>::type;
```

### <a name="parameters"></a>Параметры

*T*\
Тип для изменения.

## <a name="remarks"></a>Комментарии

Экземпляр измененного типа `add_cv<T>` имеет `type` эквивалент **typedef** для элемента *T* , измененный как [add_volatile](add-volatile-class.md) , так и [add_const](add-const-class.md), если только у *T* нет квалификаторов ОПС, является ссылкой или является функцией.

Вспомогательный тип `add_cv_t<T>` является ярлыком для доступа к определению типа `type``add_cv<T>`.

## <a name="example"></a>Пример

```cpp
// add_cv.cpp
// compile by using: cl /EHsc /W4 add_cv.cpp
#include <type_traits>
#include <iostream>

struct S {
    void f() {
        std::cout << "invoked non-cv-qualified S.f()" << std::endl;
    }
    void f() const {
        std::cout << "invoked const S.f()" << std::endl;
    }
    void f() volatile {
        std::cout << "invoked volatile S.f()" << std::endl;
    }
    void f() const volatile {
        std::cout << "invoked const volatile S.f()" << std::endl;
    }
};

template <class T>
void invoke() {
    T t;
    ((T *)&t)->f();
}

int main()
{
    invoke<S>();
    invoke<std::add_const<S>::type>();
    invoke<std::add_volatile<S>::type>();
    invoke<std::add_cv<S>::type>();
}
```

```Output
invoked non-cv-qualified S.f()
invoked const S.f()
invoked volatile S.f()
invoked const volatile S.f()
```

## <a name="requirements"></a>Требования

**Заголовок:**\<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[<type_traits>](type-traits.md)\
[Класс remove_const](remove-const-class.md)\
[Класс remove_volatile](remove-volatile-class.md)
