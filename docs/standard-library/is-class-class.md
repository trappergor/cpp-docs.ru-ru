---
title: Класс is_class | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_class
dev_langs:
- C++
helpviewer_keywords:
- is_class class
- is_class
ms.assetid: 96fc34a3-a81b-4ec6-b7fb-baafde1a0f4e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2ada95adb2d82bfccf05f3b9141a1b940feaed50
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966450"
---
# <a name="isclass-class"></a>Класс is_class

Проверяет, является ли тип классом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_class;
```

### <a name="parameters"></a>Параметры

*Ty* запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является типом, определенным как **класс** или **структуры**, или `cv-qualified` форму одного из них, в противном случае он содержит значение false.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_class.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_class<trivial> == " << std::boolalpha
        << std::is_class<trivial>::value << std::endl;
    std::cout << "is_class<int> == " << std::boolalpha
        << std::is_class<int>::value << std::endl;

    return (0);
    }

```

```Output
is_class<trivial> == true
is_class<int> == false
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс is_compound](../standard-library/is-compound-class.md)<br/>
[Класс is_union](../standard-library/is-union-class.md)<br/>
