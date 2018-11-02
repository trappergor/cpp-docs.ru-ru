---
title: Класс is_default_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_default_constructible
helpviewer_keywords:
- is_default_constructible
ms.assetid: dd8f1c44-dae5-4258-891f-c5e048d94092
ms.openlocfilehash: de991f3b9fcfec1bd7815964c6d4e19265acdb4e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565978"
---
# <a name="isdefaultconstructible-class"></a>Класс is_default_constructible

Проверяет, есть ли у типа конструктор по умолчанию.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_default_constructible;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *T* является типом класса, который имеет конструктор по умолчанию, в противном случае он содержит значение false. Это эквивалентно предикату `is_constructible<T>`. Тип *T* должно быть полным типом, **void**, или массив с неизвестной границей.

## <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

struct Simple
{
    Simple() : val(0) {}
    int val;
};

struct Simple2
{
    Simple2(int v) : val(v) {}
    int val;
};

int main()
{
    std::cout << "is_default_constructible<Simple> == " << std::boolalpha
        << std::is_default_constructible<Simple>::value << std::endl;
    std::cout << "is_default_constructible<Simple2> == " << std::boolalpha
        << std::is_default_constructible<Simple2>::value << std::endl;

    return (0);
}

```

```Output
is_default_constructible<Simple> == true
is_default_constructible<Simple2> == false
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
