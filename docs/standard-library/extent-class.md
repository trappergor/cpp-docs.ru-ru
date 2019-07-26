---
title: Класс extent
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::extent
helpviewer_keywords:
- extent class
- extent
ms.assetid: 6d16263d-90b2-4330-9ec7-b59ed898792d
ms.openlocfilehash: 0cd53ba8537e706a68ffdcf08df998108266ad20
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68457793"
---
# <a name="extent-class"></a>Класс extent

Получает измерение массива.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty, unsigned I = 0>
struct extent;
```

### <a name="parameters"></a>Параметры

*Ty*\
Запрашиваемый тип.

*СОХРАНЕНИИ*\
Массив, привязанный к запросу.

## <a name="remarks"></a>Примечания

Если *Ty* является типом массива, имеющего по крайней мере *i* единицу измерения, то запрос типа содержит количество элементов в измерении, заданном параметром *i*. Если *Ty* не является типом массива или его ранг меньше *I*, или если *i* равен нулю и *Ty* имеет `U`тип "массив с неизвестной границей", запрос типа содержит значение 0.

## <a name="example"></a>Пример

```cpp
// std__type_traits__extent.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
    {
    std::cout << "extent 0 == "
        << std::extent<int[5][10]>::value << std::endl;
    std::cout << "extent 1 == "
        << std::extent<int[5][10], 1>::value << std::endl;

    return (0);
    }
```

```Output
extent 0 == 5
extent 1 == 10
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)\
[Класс remove_all_extents](../standard-library/remove-all-extents-class.md)\
[Класс remove_extent](../standard-library/remove-extent-class.md)
