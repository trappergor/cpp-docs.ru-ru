---
title: Класс is_bind_expression
ms.date: 11/04/2016
f1_keywords:
- functional/std::is_bind_expression
helpviewer_keywords:
- is_bind_expression class
ms.assetid: 0715f9e9-2239-4778-a1cf-2c21f49dfd47
ms.openlocfilehash: f547b6f74a86612174cb0f510870171158678f7a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519422"
---
# <a name="isbindexpression-class"></a>Класс is_bind_expression

Проверяет, что тип создается путем вызова `bind`.

## <a name="syntax"></a>Синтаксис

шаблон<class Ty> is_bind_expression структуры {статический const логическое значение;};

## <a name="remarks"></a>Примечания

Член константы `value` имеет значение true, если тип `Ty` — это тип, возвращаемый вызовом метода `bind`, в противном случае — значение false.

## <a name="example"></a>Пример

```cpp
// std__functional__is_bind_expression.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

void square(double x)
{
    std::cout << x << "^2 == " << x * x << std::endl;
}

template<class Expr>
void test_for_bind(const Expr&)
{
    std::cout << std::is_bind_expression<Expr>::value << std::endl;
}

int main()
{
    test_for_bind(3.0 * 3.0);
    test_for_bind(std::bind(square, 3));

    return (0);
}
```

```Output
0
1
```

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[bind](../standard-library/functional-functions.md#bind)<br/>
