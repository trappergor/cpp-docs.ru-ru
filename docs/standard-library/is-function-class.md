---
title: Класс is_function | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is
dev_langs:
- C++
helpviewer_keywords:
- is_function class
- is
ms.assetid: e5c0dbcd-829b-415f-853f-8c5be47c5040
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7ef542ea54c0fc570443fa07908968ffa3398232
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953789"
---
# <a name="isfunction-class"></a>Класс is_function

Проверяет, является ли данный тип типом функции.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_function;
```

### <a name="parameters"></a>Параметры

*Ty* запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является типом функции, в противном случае он содержит значение false.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_function.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

struct functional
    {
    int f();
    };

int main()
    {
    std::cout << "is_function<trivial> == " << std::boolalpha
        << std::is_function<trivial>::value << std::endl;
    std::cout << "is_function<functional> == " << std::boolalpha
        << std::is_function<functional>::value << std::endl;
    std::cout << "is_function<float()> == " << std::boolalpha
        << std::is_function<float()>::value << std::endl;

    return (0);
    }

```

```Output
is_function<trivial> == false
is_function<functional> == false
is_function<float()> == true
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс is_object](../standard-library/is-object-class.md)<br/>
