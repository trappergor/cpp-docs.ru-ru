---
title: Класс is_integral
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_integral
helpviewer_keywords:
- is_integral class
- is_integral
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
ms.openlocfilehash: a367bb06f49dd2c9c64f0c257a3573add5645efe
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456242"
---
# <a name="isintegral-class"></a>Класс is_integral

Проверяет, является ли тип целочисленным.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_integral;
```

### <a name="parameters"></a>Параметры

*Ty*\
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является одним из целочисленных типов или `cv-qualified` формой одного из целочисленных типов, в противном случае — значение false.

Целочисленный тип — это один из типов **bool**, **char**, char, **без знака**, **со знаком char**, **wchar_t**, **Short**, **без знака Short**, **int**, **без знака int**, **Long**и **без знака Long**. Кроме того, с компиляторами, предоставляющими их, целочисленный тип может быть одним из длинных длинных, беззнаковых длинных, **__int64**и неподписанных **__int64**.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_integral.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_integral<trivial> == " << std::boolalpha
        << std::is_integral<trivial>::value << std::endl;
    std::cout << "is_integral<int> == " << std::boolalpha
        << std::is_integral<int>::value << std::endl;
    std::cout << "is_integral<float> == " << std::boolalpha
        << std::is_integral<float>::value << std::endl;

    return (0);
    }
```

```Output
is_integral<trivial> == false
is_integral<int> == true
is_integral<float> == false
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)\
[Класс is_enum](../standard-library/is-enum-class.md)\
[Класс is_floating_point](../standard-library/is-floating-point-class.md)
