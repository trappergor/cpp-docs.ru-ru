---
title: Класс add_const
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_const
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
ms.openlocfilehash: c82a3fac8ef95da9e226ca3e2e9122b3c8774cbf
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620831"
---
# <a name="add_const-class"></a>Класс add_const

Создает тип const из типа.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
struct add_const;
```

### <a name="parameters"></a>Параметры

*Ty*\
Тип для изменения.

## <a name="remarks"></a>Комментарии

Экземпляр модификатора типа содержит модифицированный тип, *Ty* , если *Ty* является ссылкой, функцией или типом с квалификатором const, в противном случае `const Ty` .

## <a name="example"></a>Пример

```cpp
// std__type_traits__add_const.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
{
    std::add_const<int>::type *p = (const int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_const<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_const<int> == int
```

## <a name="requirements"></a>Требования

**Заголовок:**\<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также раздел

[<type_traits>](type-traits.md)\
[Класс remove_const](remove-const-class.md)
