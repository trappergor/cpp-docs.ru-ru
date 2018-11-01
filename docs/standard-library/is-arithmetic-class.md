---
title: Класс is_arithmetic
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_arithmetic
helpviewer_keywords:
- is_arithmetic class
- is_arithmetic
ms.assetid: ea427b7e-0141-4a04-848f-561054c53001
ms.openlocfilehash: 7aff4b051786c3d77dacb65ddbdbd29fa695ca48
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520657"
---
# <a name="isarithmetic-class"></a>Класс is_arithmetic

Проверяет, является ли тип арифметическим.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_arithmetic;
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является арифметический тип, то есть целочисленный тип или число с плавающей запятой, или `cv-qualified` форму одного из них, в противном случае он содержит значение false.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_arithmetic.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_arithmetic<trivial> == " << std::boolalpha
        << std::is_arithmetic<trivial>::value << std::endl;
    std::cout << "is_arithmetic<int> == " << std::boolalpha
        << std::is_arithmetic<int>::value << std::endl;
    std::cout << "is_arithmetic<float> == " << std::boolalpha
        << std::is_arithmetic<float>::value << std::endl;

    return (0);
    }
```

```Output
is_arithmetic<trivial> == false
is_arithmetic<int> == true
is_arithmetic<float> == true
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс is_floating_point](../standard-library/is-floating-point-class.md)<br/>
[Класс is_integral](../standard-library/is-integral-class.md)<br/>
