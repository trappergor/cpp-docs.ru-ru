---
title: Класс is_array | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_array
dev_langs:
- C++
helpviewer_keywords:
- is_array class
- is_array
ms.assetid: 61fb2201-8de3-4746-9721-617f02df170f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 64f4594044ce135ed6927f9d0108863cca12845d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33844098"
---
# <a name="isarray-class"></a>Класс is_array

Проверяет, является ли тип массивом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_array;
```

### <a name="parameters"></a>Параметры

`Ty` Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип `Ty` является массивом, в противном случае — значение false.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_array.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_array<trivial> == " << std::boolalpha
        << std::is_array<trivial>::value << std::endl;
    std::cout << "is_array<int> == " << std::boolalpha
        << std::is_array<int>::value << std::endl;
    std::cout << "is_array<int[5]> == " << std::boolalpha
        << std::is_array<int[5]>::value << std::endl;

    return (0);
    }
```

```Output
is_array<trivial> == false
is_array<int> == false
is_array<int[5]> == true
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс extent](../standard-library/extent-class.md)<br/>
[Класс rank](../standard-library/rank-class.md)<br/>
