---
title: Объект _1
ms.date: 11/04/2016
f1_keywords:
- _1
- std::_1
- functional/std::_1
helpviewer_keywords:
- _1 object
ms.assetid: 30c3c480-ff31-4708-94be-7d0d65f243c9
ms.openlocfilehash: 248bb4733849b231ee4ff9180dd04e288412af3b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666370"
---
# <a name="1-object"></a>Объект _1

Заполнители для подстановочных аргументов.

## <a name="syntax"></a>Синтаксис

```cpp
namespace placeholders {
    extern unspecified _1,
    _2, ... _M
} // namespace placeholders (within std)
```

## <a name="remarks"></a>Примечания

Объекты `_1, _2, ... _M` — это местозаполнители первой, второй,..., m-й аргумент соответственно в вызове функции в объект, возвращаемый [привязать](../standard-library/functional-functions.md#bind). Можно использовать `_N` для указания, куда необходимо вставить N-й аргумент при вычислении выражения привязки.

В этой реализации значение `M` — 20.

## <a name="example"></a>Пример

```cpp
// std__functional_placeholder.cpp
// compile with: /EHsc
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std::placeholders;

void square(double x)
    {
    std::cout << x << "^2 == " << x * x << std::endl;
    }

void product(double x, double y)
    {
    std::cout << x << "*" << y << " == " << x * y << std::endl;
    }

int main()
    {
    double arg[] = {1, 2, 3};

    std::for_each(&arg[0], &arg[3], square);
    std::cout << std::endl;

    std::for_each(&arg[0], &arg[3], std::bind(product, _1, 2));
    std::cout << std::endl;

    std::for_each(&arg[0], &arg[3], std::bind(square, _1));

    return (0);
    }

```

```Output
1^2 == 1
2^2 == 4
3^2 == 9

1*2 == 2
2*2 == 4
3*2 == 6

1^2 == 1
2^2 == 4
3^2 == 9
```

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[bind](../standard-library/functional-functions.md#bind)<br/>
[Класс is_placeholder](../standard-library/is-placeholder-class.md)<br/>
