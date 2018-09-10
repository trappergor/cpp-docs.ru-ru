---
title: Класс is_scalar | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_scalar
dev_langs:
- C++
helpviewer_keywords:
- is_scalar class
- is_scalar
ms.assetid: a0cdfc9a-f27e-4808-890f-6ed7942db60c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c0dae274d1f3aa61e2e8f2d3000b277edb0debd
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107020"
---
# <a name="isscalar-class"></a>Класс is_scalar

Проверяет, является ли тип скалярным.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_scalar;
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* это целочисленный тип, с плавающей запятой тип, тип перечисления, тип указателя или указатель на тип элемента, или `cv-qualified` форму одного из них, в противном случае он содержит значение false.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_scalar.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_scalar<trivial> == " << std::boolalpha
        << std::is_scalar<trivial>::value << std::endl;
    std::cout << "is_scalar<trivial *> == " << std::boolalpha
        << std::is_scalar<trivial *>::value << std::endl;
    std::cout << "is_scalar<int> == " << std::boolalpha
        << std::is_scalar<int>::value << std::endl;
    std::cout << "is_scalar<float> == " << std::boolalpha
        << std::is_scalar<float>::value << std::endl;

    return (0);
    }

```

```Output
is_scalar<trivial> == false
is_scalar<trivial *> == true
is_scalar<int> == true
is_scalar<float> == true
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс is_compound](../standard-library/is-compound-class.md)<br/>
