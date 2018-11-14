---
title: Класс is_enum
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_enum
helpviewer_keywords:
- is_enum class
- is_enum
ms.assetid: df3b00b7-4f98-4b3a-96ce-10ad958ee69c
ms.openlocfilehash: 623bda13a12ac311618e1b9fffdbc3f676013df6
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51517596"
---
# <a name="isenum-class"></a>Класс is_enum

Проверяет, является ли тип перечислением.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_enum;
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является типом перечисления или `cv-qualified` форму типа перечисления, в противном случае он содержит значение false.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_enum.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

enum color {
    red, greed, blue};

int main()
    {
    std::cout << "is_enum<trivial> == " << std::boolalpha
        << std::is_enum<trivial>::value << std::endl;
    std::cout << "is_enum<color> == " << std::boolalpha
        << std::is_enum<color>::value << std::endl;
    std::cout << "is_enum<int> == " << std::boolalpha
        << std::is_enum<int>::value << std::endl;

    return (0);
    }
```

```Output
is_enum<trivial> == false
is_enum<color> == true
is_enum<int> == false
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс is_integral](../standard-library/is-integral-class.md)<br/>
