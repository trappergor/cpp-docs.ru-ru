---
title: Класс add_volatile
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_volatile
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
ms.openlocfilehash: 1a4ad8a86b88cdfa98f043bb49ba6eeff8b090c9
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619205"
---
# <a name="add_volatile-class"></a>Класс add_volatile

Создает тип **volatile** из указанного типа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct add_volatile;

template <class T>
using add_volatile_t = typename add_volatile<T>::type;
```

### <a name="parameters"></a>Параметры

*T*\
Тип для изменения.

## <a name="remarks"></a>Комментарии

`add_volatile<T>`У экземпляра есть **typedef** члена `type` , который имеет тип *t* , если *t* является ссылкой, функцией или типом с квалификатором, в противном случае — **переменную** *t*. Псевдоним `add_volatile_t` является ярлыком для доступа к определению **типа** члена `type` .

## <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_volatile_t<int> *p = (volatile int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_volatile<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_volatile<int> == int
```

## <a name="requirements"></a>Требования

**Заголовок:**\<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[<type_traits>](type-traits.md)\
[Класс remove_volatile](remove-volatile-class.md)
