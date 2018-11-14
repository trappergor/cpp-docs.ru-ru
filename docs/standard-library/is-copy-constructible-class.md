---
title: Класс is_copy_constructible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_copy_constructible
helpviewer_keywords:
- is_copy_constructible
ms.assetid: d8db9d4c-21ed-4884-bead-0b0b562de007
ms.openlocfilehash: c85d036efda2509885a079cf59a130a63c0389bc
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521171"
---
# <a name="iscopyconstructible-class"></a>Класс is_copy_constructible

Проверяет, есть ли у типа конструктор копии.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct is_copy_constructible;
```

### <a name="parameters"></a>Параметры

*Ty*<br/>
Запрашиваемый тип.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип *Ty* является классом, имеющим конструктор копии, в противном случае он содержит значение false.

## <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

struct Copyable
{
    int val;
};

struct NotCopyable
{
   NotCopyable(const NotCopyable&) = delete;
   int val;

};

int main()
{
    std::cout << "is_copy_constructible<Copyable> == " << std::boolalpha
        << std::is_copy_constructible<Copyable>::value << std::endl;
    std::cout << "is_copy_constructible<NotCopyable> == " << std::boolalpha
        << std::is_copy_constructible<NotCopyable>::value << std::endl;

    return (0);
}
```

```Output
is_copy_constructible<Copyable> == true
is_copy_constructible<NotCopyable > == false
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
