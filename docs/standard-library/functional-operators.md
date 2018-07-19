---
title: Операторы &lt;functional&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::operator!=
- functional/std::operator==
dev_langs:
- C++
helpviewer_keywords:
- functional operators
ms.assetid: d4b3c760-f3e2-4b65-bdaa-d42e8dd6f5e1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b9bc37213ed2e5690f85fca738d44e6eecfaa8c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962053"
---
# <a name="ltfunctionalgt-operators"></a>Операторы &lt;functional&gt;

|||
|-|-|
|[оператор!=](#op_neq)|[оператор==](#op_eq_eq)|

## <a name="op_eq_eq"></a> operator==

Проверяет, является ли вызываемый объект пустым.

```cpp
template <class Fty>
bool operator==(const function<Fty>& f, null_ptr_type npc);

template <class Fty>
bool operator==(null_ptr_type npc, const function<Fty>& f);
```

### <a name="parameters"></a>Параметры

*Fty* тип функции программы-оболочки.

*f* объект-функцию

*NPC* является пустым указателем.

### <a name="remarks"></a>Примечания

Операторы принимают аргумент, являющийся ссылкой на объект `function`, и аргумент, являющийся константой указателя null. В обоих случаях возвращается значение true только в том случае, если объект `function` пуст.

### <a name="example"></a>Пример

```cpp
// std__functional__operator_eq.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
{
    return (-val);
}

int main()
{
    std::function<int(int)> fn0;
    std::cout << std::boolalpha << "empty == "
        << (fn0 == 0) << std::endl;

    std::function<int(int)> fn1(neg);
    std::cout << std::boolalpha << "empty == "
        << (fn1 == 0) << std::endl;

    return (0);
}

```

```Output
empty == true
empty == false
```

## <a name="op_neq"></a> operator!=

Проверяет, является ли вызываемый объект не пустым.

```cpp
template <class Fty>
bool operator!=(const function<Fty>& f, null_ptr_type npc);

template <class Fty>
bool operator!=(null_ptr_type npc, const function<Fty>& f);
```

### <a name="parameters"></a>Параметры

*Fty* тип функции программы-оболочки.

*f* объект-функцию

*NPC* является пустым указателем.

### <a name="remarks"></a>Примечания

Операторы принимают аргумент, являющийся ссылкой на объект `function`, и аргумент, являющийся константой указателя null. В обоих случаях возвращается значение true только в том случае, если объект `function` не пуст.

### <a name="example"></a>Пример

```cpp
// std__functional__operator_ne.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0;
    std::cout << std::boolalpha << "not empty == "
        << (fn0 != 0) << std::endl;

    std::function<int (int)> fn1(neg);
    std::cout << std::boolalpha << "not empty == "
        << (fn1 != 0) << std::endl;

    return (0);
    }

```

```Output
not empty == false
not empty == true
```

## <a name="see-also"></a>См. также

[\<functional>](../standard-library/functional.md)<br/>
