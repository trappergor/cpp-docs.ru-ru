---
title: Класс is_convertible
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_convertible
helpviewer_keywords:
- is_convertible class
- is_convertible
ms.assetid: 75614008-1894-42ea-bd57-974399628536
ms.openlocfilehash: 1df87299d0b06ccfd2bef05bab89a9241f27d57d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50583564"
---
# <a name="isconvertible-class"></a>Класс is_convertible

Проверяет, можно ли преобразовать один тип в другой.

## <a name="syntax"></a>Синтаксис

```cpp
template <class From, class To>
struct is_convertible;
```

### <a name="parameters"></a>Параметры

*From*<br/>
Преобразовываемый тип.

*Ty*<br/>
Целевой тип преобразования.

## <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если выражение `To to = from;`, где `from` является объектом типа `From`, имеет правильный формат.

## <a name="example"></a>Пример

```cpp
// std__type_traits__is_convertible.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_convertible<trivial, int> == " << std::boolalpha
        << std::is_convertible<trivial, int>::value << std::endl;
    std::cout << "is_convertible<trivial, trivial> == " << std::boolalpha
        << std::is_convertible<trivial, trivial>::value << std::endl;
    std::cout << "is_convertible<char, int> == " << std::boolalpha
        << std::is_convertible<char, int>::value << std::endl;

    return (0);
    }

```

```Output
is_convertible<trivial, int> == false
is_convertible<trivial, trivial> == true
is_convertible<char, int> == true
```

## <a name="requirements"></a>Требования

**Заголовок:** \<type_traits>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
[Класс is_base_of](../standard-library/is-base-of-class.md)<br/>
