---
title: Операторы &lt;tuple&gt;
ms.date: 11/04/2016
f1_keywords:
- tuple/std::operator!=
- tuple/std::operator>
- tuple/std::operator>=
- tuple/std::operator<
- tuple/std::operator<=
- tuple/std::operator==
ms.assetid: f25752dc-d3e2-4e12-b5ac-9a8682ca60ed
ms.openlocfilehash: 5554f08f32048bafde5bdb2c316e12e1e01c6ffb
ms.sourcegitcommit: 19016630f9d35f365e9ba249e0f3617515d7ca33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/20/2020
ms.locfileid: "92274628"
---
# <a name="lttuplegt-operators"></a>Операторы &lt;tuple&gt;

## <a name="operator"></a><a name="op_neq"></a> operator! =

Сравнивает объекты `tuple` на неравенство.

```cpp
template <class T1, class T2, ..., class TN,
    class U1, class U2, ..., class UN>
bool operator!=(const tuple<T1, T2, ..., TN>& tpl1,
    const tuple<U1, U2, ..., UN>& tpl2);
```

### <a name="parameters"></a>Параметры

*КОД*\
Тип N-го элемента кортежа.

### <a name="remarks"></a>Remarks

Функция возвращает значение false, если `N` равно 0; в противном случае — значение `get<0>(tpl1) != get<0>(tpl2) || get<1>(tpl1) != get<1>(tpl2) || ... || get<N - 1>(tpl1) == get<N - 1>(tpl2)`.

### <a name="example"></a>Пример

```cpp
// std__tuple__operator_ne.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1 = std::make_tuple(4, 5, 6, 7);

// display contents " 4 5 6 7"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 != c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 != c1);
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0 1 2 3
false
true
```

## <a name="operatorlt"></a><a name="op_lt"></a> станции&lt;

Сравнение объектов `tuple` на предмет меньшинства.

```cpp
template <class T1, class T2, ..., class TN,
    class U1, class U2, ..., class UN>
bool operator<(const tuple<T1, T2, ..., TN>& tpl1,
    const tuple<U1, U2, ..., UN>& tpl2);
```

### <a name="parameters"></a>Параметры

*КОД*\
Тип N-го элемента кортежа.

### <a name="remarks"></a>Remarks

Функция возвращает значение true, если `N` больше 0, а первое отличающееся значение в `tpl1` при сравнении оказывается меньше, чем соответствующее значение `tpl2`; в противном случае возвращается значение false.

### <a name="example"></a>Пример

```cpp
// std__tuple__operator_lt.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1 = std::make_tuple(4, 5, 6, 7);

// display contents " 4 5 6 7"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 < c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 < c1);
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0 1 2 3
false
true
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a> станции&lt;=

Сравнение объектов `tuple` на предмет отношения меньше или равно.

```cpp
template <class T1, class T2, ..., class TN,
    class U1, class U2, ..., class UN>
bool operator<=(const tuple<T1, T2, ..., TN>& tpl1,
    const tuple<U1, U2, ..., UN>& tpl2);
```

### <a name="parameters"></a>Параметры

*КОД*\
Тип N-го элемента кортежа.

### <a name="remarks"></a>Remarks

Функция возвращает `!(tpl2 < tpl1)`.

### <a name="example"></a>Пример

```cpp
// std__tuple__operator_le.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1 = std::make_tuple(4, 5, 6, 7);

// display contents " 4 5 6 7"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 <= c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c1 <= c0);
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0 1 2 3
true
false
```

## <a name="operator"></a><a name="op_eq_eq"></a> Оператор = =

Сравнение объектов `tuple` на равенство.

```cpp
template <class T1, class T2, ..., class TN,
    class U1, class U2, ..., class UN>
bool operator==(const tuple<T1, T2, ..., TN>& tpl1,
    const tuple<U1, U2, ..., UN>& tpl2);
```

### <a name="parameters"></a>Параметры

*КОД*\
Тип N-го элемента кортежа.

### <a name="remarks"></a>Remarks

Функция возвращает значение true, если `N` равно 0; в противном случае — значение `get<0>(tpl1) == get<0>(tpl2) && get<1>(tpl1) == get<1>(tpl2) && ... && get<N - 1>(tpl1) == get<N - 1>(tpl2)`.

### <a name="example"></a>Пример

```cpp
// std__tuple__operator_eq.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1 = std::make_tuple(4, 5, 6, 7);

// display contents " 4 5 6 7"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 == c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 == c1);
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0 1 2 3
true
false
```

## <a name="operatorgt"></a><a name="op_gt"></a> станции&gt;

Сравнение объектов `tuple` на предмет большинства.

```cpp
template <class T1, class T2, ..., class TN,
    class U1, class U2, ..., class UN>
bool operator>(const tuple<T1, T2, ..., TN>& tpl1,
    const tuple<U1, U2, ..., UN>& tpl2);
```

### <a name="parameters"></a>Параметры

*КОД*\
Тип N-го элемента кортежа.

### <a name="remarks"></a>Remarks

Функция возвращает `tpl2 < tpl1`.

### <a name="example"></a>Пример

```cpp
// std__tuple__operator_gt.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1 = std::make_tuple(4, 5, 6, 7);

// display contents " 4 5 6 7"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 > c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c1 > c0);
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0 1 2 3
false
true
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a> станции&gt;=

Сравнение объектов `tuple` на предмет большинства или равенства.

```cpp
template <class T1, class T2, ..., class TN,
    class U1, class U2, ..., class UN>
bool operator>=(const tuple<T1, T2, ..., TN>& tpl1,
    const tuple<U1, U2, ..., UN>& tpl2);
```

### <a name="parameters"></a>Параметры

*КОД*\
Тип N-го элемента кортежа.

### <a name="remarks"></a>Remarks

Функция возвращает `!(tpl1 < tpl2)`.

### <a name="example"></a>Пример

```cpp
// std__tuple__operator_ge.cpp
// compile with: /EHsc
#include <tuple>
#include <iostream>

typedef std::tuple<int, double, int, double> Mytuple;
int main() {
    Mytuple c0(0, 1, 2, 3);

// display contents " 0 1 2 3"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

    Mytuple c1 = std::make_tuple(4, 5, 6, 7);

// display contents " 4 5 6 7"
    std::cout << " " << std::get<0>(c0);
    std::cout << " " << std::get<1>(c0);
    std::cout << " " << std::get<2>(c0);
    std::cout << " " << std::get<3>(c0);
    std::cout << std::endl;

// display results of comparisons
    std::cout << std::boolalpha << " " << (c0 >= c0);
    std::cout << std::endl;
    std::cout << std::boolalpha << " " << (c0 >= c1);
    std::cout << std::endl;

    return (0);
}
```

```Output
0 1 2 3
0 1 2 3
true
false
```
