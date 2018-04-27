---
title: Класс add_cv | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::add_cv
dev_langs:
- C++
helpviewer_keywords:
- add_cv class
- add_cv
ms.assetid: a5572c78-a097-45d7-b476-ed4876889dea
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f5996fb3490d15947c825077ea963ac08b20c546
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="addcv-class"></a>Класс add_cv

Создает константный долговременный тип из типа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class T>
struct add_cv;

template <class T>
using add_cv_t = typename add_cv<T>::type;
```

### <a name="parameters"></a>Параметры

*T* тип для изменения.

## <a name="remarks"></a>Примечания

Экземпляр измененного типа `add_cv<T>` имеет определение типа члена `type`, эквивалентное *T*, измененному и [add_volatile](../standard-library/add-volatile-class.md), и [add_const](../standard-library/add-const-class.md), кроме случая, когда *T* уже имеет cv-квалификаторы, является ссылкой или функцией.

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

**Заголовок:** \<type_traits > **пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс remove_const](../standard-library/remove-const-class.md)<br/>
[Класс remove_volatile](../standard-library/remove-volatile-class.md)<br/>
