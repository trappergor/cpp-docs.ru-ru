---
title: Класс is_empty
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_empty
helpviewer_keywords:
- is_empty class
- is_empty
ms.assetid: 44a6fc92-7e55-4fbe-9a24-2a0ce2dccba0
ms.openlocfilehash: 6300107ecf9c4ea1e237a60bf18f26b6416f7fba
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68452710"
---
# <a name="isempty-class"></a>Класс is_empty

Проверяет, является ли тип пустым классом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_empty;
```

### <a name="parameters"></a>Параметры

*Ty*\
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является пустым классом, в противном случае — значение false.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_empty.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct empty
    {
    };

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_empty<trivial> == " << std::boolalpha
        << std::is_empty<trivial>::value << std::endl;
    std::cout << "is_empty<empty> == " << std::boolalpha
        << std::is_empty<empty>::value << std::endl;
    std::cout << "is_empty<int> == " << std::boolalpha
        << std::is_empty<int>::value << std::endl;

    return (0);
    }
```

```Output
is_empty<trivial> == false
is_empty<empty> == true
is_empty<int> == false
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)
