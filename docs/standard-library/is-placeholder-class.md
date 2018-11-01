---
title: Класс is_placeholder
ms.date: 11/04/2016
f1_keywords:
- functional/std::is_placeholder
helpviewer_keywords:
- is_placeholder class
ms.assetid: 2b21a792-96d1-4bb8-b911-0db796510835
ms.openlocfilehash: 2c7848c88194a9b541867b26ffe27764ad862503
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613737"
---
# <a name="isplaceholder-class"></a>Класс is_placeholder

Проверяет, является ли тип заполнителем.

## <a name="syntax"></a>Синтаксис

Структура is_placeholder {статическое const int значение;};

## <a name="remarks"></a>Примечания

Значение константы `value` равно 0, если тип `Ty` не является заполнителем. В противном случае значение — это положение аргумента вызова функции, к которому он привязывается. Используется для определения значения `N` n-ного заполнителя `_N`.

## <a name="example"></a>Пример

```cpp
// std__functional__is_placeholder.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

using namespace std::placeholders;

template<class Expr>
void test_for_placeholder(const Expr&)
{
    std::cout << std::is_placeholder<Expr>::value << std::endl;
}

int main()
{
    test_for_placeholder(3.0);
    test_for_placeholder(_3);

    return (0);
}
```

```Output
0
3
```

## <a name="requirements"></a>Требования

**Заголовок:** \<functional>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Объект _1](../standard-library/1-object.md)<br/>
