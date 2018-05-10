---
title: Класс is_floating_point | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_floating_point
dev_langs:
- C++
helpviewer_keywords:
- is_floating_point class
- is_floating_point
ms.assetid: 070679c1-115b-4ee4-8ab7-f52e5d9e157f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 63129ad04e2e74cdae9c590c76e1910e95117431
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="isfloatingpoint-class"></a>Класс is_floating_point

Проверяет, является ли тип типом с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_floating_point;
```

### <a name="parameters"></a>Параметры

`Ty` Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип `Ty` является типом с плавающей запятой или формой `cv-qualified` типа с плавающей запятой, в противном случае — значение false.

Тип с плавающей запятой является одним из следующих типов: `float`, `double` или `long double`.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_floating_point.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_floating_point<trivial> == " << std::boolalpha
        << std::is_floating_point<trivial>::value << std::endl;
    std::cout << "is_floating_point<int> == " << std::boolalpha
        << std::is_floating_point<int>::value << std::endl;
    std::cout << "is_floating_point<float> == " << std::boolalpha
        << std::is_floating_point<float>::value << std::endl;

    return (0);
    }

```

```Output
is_floating_point<trivial> == false
is_floating_point<int> == false
is_floating_point<float> == true
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс is_integral](../standard-library/is-integral-class.md)<br/>
