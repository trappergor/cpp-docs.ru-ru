---
title: Класс is_abstract
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_abstract
helpviewer_keywords:
- is_abstract class
- is_abstract
ms.assetid: 8867f660-3434-404c-ba90-c26607a5e0d2
ms.openlocfilehash: 57b2413e673f92e5258bee5711db2870e2b58a11
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448987"
---
# <a name="isabstract-class"></a>Класс is_abstract

Проверяет, является ли тип абстрактным классом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_abstract;
```

### <a name="parameters"></a>Параметры

*Ty*\
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является классом, имеющим по крайней мере одну чисто виртуальную функцию, в противном случае — значение false.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_abstract.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

struct abstract
    {
    virtual int val() = 0;
    };

int main()
    {
    std::cout << "is_abstract<trivial> == " << std::boolalpha
        << std::is_abstract<trivial>::value << std::endl;
    std::cout << "is_abstract<abstract> == " << std::boolalpha
        << std::is_abstract<abstract>::value << std::endl;

    return (0);
    }
```

```Output
is_abstract<trivial> == false
is_abstract<abstract> == true
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)\
Класс [is_polymorphic](../standard-library/is-polymorphic-class.md)
