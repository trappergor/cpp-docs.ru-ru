---
title: Класс is_integral | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_integral
dev_langs:
- C++
helpviewer_keywords:
- is_integral class
- is_integral
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 531ee45aed64daa19f818bc5c8480a9c1b032d30
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="isintegral-class"></a>Класс is_integral

Проверяет, является ли тип целочисленным.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_integral;
```

### <a name="parameters"></a>Параметры

`Ty` Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа имеет значение true, если тип `Ty` является одним из целочисленных типов или формой `cv-qualified` одного из целочисленных типов, , в противном случае — значение false.

Целочисленный тип — один из типов `bool`, `char`, `unsigned char`, `signed char`, `wchar_t`, `short`, `unsigned short`, `int`, `unsigned int`, `long` и `unsigned long`. Кроме того, целочисленный тип может быть одним из `long long`, `unsigned long long`, `__int64` и `unsigned __int64` при использовании компиляторов, поддерживающих такие типы.

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

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс is_enum](../standard-library/is-enum-class.md)<br/>
[Класс is_floating_point](../standard-library/is-floating-point-class.md)<br/>
