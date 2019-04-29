---
title: Класс is_base_of
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_base_of
helpviewer_keywords:
- is_base_of class
- is_base_of
ms.assetid: 436f6213-1d4c-4ffc-a588-fc7c4887dd86
ms.openlocfilehash: 345301b5eeed7b66f18a54e56b9bee6346078634
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383676"
---
# <a name="isbaseof-class"></a>Класс is_base_of

Проверяет, является ли один тип базовым для другого.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Base, class Derived>
struct is_base_of;
```

### <a name="parameters"></a>Параметры

*Base*<br/>
Базовый класс для проверки.

*Производные*<br/>
Производный тип для проверки.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *базового* является базовым классом типа *Derived*, в противном случае он содержит значение false.

## <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

struct base
    {
    int val;
    };

struct derived
    : public base
    {
    };

int main()
    {
    std::cout << "is_base_of<base, base> == " << std::boolalpha
        << std::is_base_of<base, base>::value << std::endl;
    std::cout << "is_base_of<base, derived> == " << std::boolalpha
        << std::is_base_of<base, derived>::value << std::endl;
    std::cout << "is_base_of<derived, base> == " << std::boolalpha
        << std::is_base_of<derived, base>::value << std::endl;

    return (0);
    }
```

```Output
is_base_of<base, base> == true
is_base_of<base, derived> == true
is_base_of<derived, base> == false
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс is_convertible](../standard-library/is-convertible-class.md)<br/>
