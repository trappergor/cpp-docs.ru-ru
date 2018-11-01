---
title: __func__
ms.date: 10/19/2017
f1_keywords:
- __func__
ms.assetid: a5299b8d-f0ee-4af2-91dd-8fb165e68798
ms.openlocfilehash: eecd3efea6239c92a8bc81c0ed13a9563e5b87d2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438588"
---
# <a name="func"></a>__func__

**(C ++ 11)**  Предопределенный идентификатор &#95; &#95;func&#95; &#95; неявно определяется как строка, содержащая Неквалифицированное и недополненное имя включающей функции. &#95;&#95;Func&#95; &#95; является обязательным компонентом стандарта C++ и не является расширением Майкрософт.

## <a name="syntax"></a>Синтаксис

```cpp
__func__
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает, заканчивающаяся нулевым символом const char массив символов, содержащий имя функции.

## <a name="example"></a>Пример

```cpp
#include <string>
#include <iostream>

namespace Test
{
    struct Foo
    {
        static void DoSomething(int i, std::string s)
        {
           std::cout << __func__ << std::endl; // Output: DoSomething
        }
    };
}

int main()
{
    Test::Foo::DoSomething(42, "Hello");

    return 0;
}
```

## <a name="requirements"></a>Требования

C++11