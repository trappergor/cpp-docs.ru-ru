---
title: Функции &lt;functional&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::bind
- xfunctional/std::bind1st
- xfunctional/std::bind2nd
- xfunctional/std::bit_and
- xfunctional/std::bit_not
- xfunctional/std::bit_or
- xfunctional/std::bit_xor
- functional/std::cref
- type_traits/std::cref
- xfunctional/std::mem_fn
- xfunctional/std::mem_fun_ref
- xfunctional/std::not1
- xfunctional/std::not2
- xfunctional/std::ptr_fun
- functional/std::ref
- functional/std::swap
dev_langs:
- C++
helpviewer_keywords:
- std::bind [C++]
- std::bind1st
- std::bind2nd
- std::bit_and [C++]
- std::bit_not [C++]
- std::bit_or [C++]
- std::bit_xor [C++]
- std::cref [C++]
ms.assetid: c34d0b45-50a7-447a-9368-2210d06339a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b14e656d77247984ba3306d6efff78e6cca713cb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="ltfunctionalgt-functions"></a>Функции &lt;functional&gt;

||||
|-|-|-|
|[bind](#bind)|[bind1st](#bind1st)|[bind2nd](#bind2nd)|
|[bit_and](#bit_and)|[bit_not](#bit_not)|[bit_or](#bit_or)|
|[bit_xor](#bit_xor)|[cref](#cref)|[mem_fn](#mem_fn)|
|[mem_fun](#mem_fun)|[mem_fun_ref](#mem_fun_ref)|[not1](#not1)|
|[not2](#not2)|[ptr_fun](#ptr_fun)|[ref](#ref)|
|[swap](#swap)|

## <a name="bind"></a>  bind

Привязывает аргументы к вызываемому объекту.

```cpp
template <class Fty, class T1, class T2, ..., class TN>
unspecified bind(Fty fn, T1 t1, T2 t2, ..., TN tN);

template <class Ret, class Fty, class T1, class T2, ..., class TN>
unspecified bind(Fty fn, T1 t1, T2 t2, ..., TN tN);
```

### <a name="parameters"></a>Параметры

`Fty` Тип объекта для вызова.

`TN` Тип n-го вызова аргумента.

`fn` Объект для вызова.

`tN` Вызов n-й аргумент.

### <a name="remarks"></a>Примечания

Типы `Fty, T1, T2, ..., TN` должны быть конструируемыми по копии, а `INVOKE(fn, t1, ..., tN)` должен быть действительным выражением для некоторых значений `w1, w2, ..., wN`.

Первая шаблонная функция возвращает пересылающую оболочку вызова `g` со слабым типом результата. Влияние `g(u1, u2, ..., uM)` — `INVOKE(f, v1, v2, ..., vN, ` [result_of](../standard-library/result-of-class.md)`<Fty cv (V1, V2, ..., VN)>::type)`, где `cv` является cv квалификаторы из `g` значения и типы аргументов, связанных `v1, v2, ..., vN` определяются как указанными ниже. Его можно использовать для привязки к вызываемому объекту, чтобы создать вызываемый объект с адаптированным списком аргументов.

Вторая шаблонная функция возвращает пересылающую оболочку вызова `g` с вложенным типом `result_type`, который является синонимом для `Ret`. Эффект `g(u1, u2, ..., uM)` — `INVOKE(f, v1, v2, ..., vN, Ret)`, где `cv` — CV-квалификаторы `g`, а значения и типы привязанных аргументов `v1, v2, ..., vN` определяются следующим образом. Его можно использовать для привязки к вызываемому объекту, чтобы создать вызываемый объект с адаптированным списком аргументов и заданным типом возвращаемого значения.

Значения привязанных аргументов `v1, v2, ..., vN` и их соответствующие типы `V1, V2, ..., VN` зависят от типа соответствующего аргумента `ti` типа `Ti` в вызове функции `bind` и CV-квалификаторах `cv` оболочки вызова `g` следующим образом:

если `ti` имеет тип `reference_wrapper<T>`, аргумент `vi` имеет значение `ti.get()`, и его тип `Vi` — `T&`;

если `std::is_bind_expression<Ti>::value` имеет значение `true`, аргумент `vi` имеет значение `ti(u1, u2, ..., uM)`, и его тип `Vi` — `result_of<Ti` `cv` `(U1&, U2&, ..., UN&>::type`;

если значение `j` для `std::is_placeholder<Ti>::value` отлично от нуля, аргумент `vi` имеет значение `uj`, и его тип `Vi` — `Uj&`;

в противном случае аргумент `vi` имеет значение `ti`, а его тип `Vi` — `Ti` `cv` `&`.

Например, в случае функции `f(int, int)` выражение `bind(f, _1, 0)` возвращает пересылающую оболочку вызова `cw`, чтобы `cw(x)` вызывал `f(x, 0)`. Выражение `bind(f, 0, _1)` возвращает пересылающую оболочку вызова `cw`, чтобы `cw(x)` вызывал `f(0, x)`.

Число аргументов в вызове в `bind` помимо аргумента `fn` должно быть равно числу аргументов, которые могут быть переданы в вызываемый объект `fn`. Таким образом, `bind(cos, 1.0)` верно, а `bind(cos)` и `bind(cos, _1, 0.0)` неверны.

Число аргументов в вызове функции, отправляемом в оболочку вызова, возвращаемом методом `bind`, должен быть не меньше наивысшего нумерованного значения `is_placeholder<PH>::value` для всех аргументов-местозаполнителей в вызове в `bind`. Таким образом, `bind(cos, _2)(0.0, 1.0)` верно (и возвращает `cos(1.0)`), а `bind(cos, _2)(0.0)` неверно.

### <a name="example"></a>Пример

```cpp
// std__functional__bind.cpp
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
    double arg[] = { 1, 2, 3 };

    std::for_each(&arg[0], arg + 3, square);
    std::cout << std::endl;

    std::for_each(&arg[0], arg + 3, std::bind(product, _1, 2));
    std::cout << std::endl;

    std::for_each(&arg[0], arg + 3, std::bind(square, _1));

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

## <a name="bind1st"></a>  bind1st

Вспомогательная функция шаблона, которая создает адаптер для преобразования объекта бинарной функции в объект унарной функции, привязывая первый аргумент бинарной функции к указанному значению.

```cpp
template <class Operation, class Type>
binder1st <Operation> bind1st (const Operation& func, const Type& left);
```

### <a name="parameters"></a>Параметры

`func` Объект бинарной функции для преобразования в объект унарной функции.

`left` Значение, к которому привязан первый аргумент бинарной функции объекта.

### <a name="return-value"></a>Возвращаемое значение

Объект функции унарный, полученный в результате привязывая первый аргумент бинарной функции объекта значение `left`.

### <a name="remarks"></a>Примечания

Модули привязки функций — это разновидность адаптера функций. Так как они возвращают объекты функций, их можно использовать в композициях функций некоторого типа для создания более сложных и мощных выражений.

Если `func` — объект типа `Operation`, а `c` — константа, то `bind1st` ( `func`, `c`) эквивалентен [binder1st](../standard-library/binder1st-class.md) конструктора класса `binder1st` <  `Operation`> ( `func`, `c`) и является более удобным.

### <a name="example"></a>Пример

```cpp
// functional_bind1st.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

// Creation of a user-defined function object
// that inherits from the unary_function base class
class greaterthan5: unary_function<int, bool>
{
public:
    result_type operator()(argument_type i)
    {
        return (result_type)(i > 5);
    }
};

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( " ;
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1a;
    result1a = count_if(v1.begin(), v1.end(), bind1st(less<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1a << "." << endl;

    // Compare: counting the number of integers > 5 in the vector
    // with a user defined function object
    vector<int>::iterator::difference_type result1b;
    result1b = count_if(v1.begin(), v1.end(), greaterthan5());
    cout << "The number of elements in v1 greater than 5 is: "
         << result1b << "." << endl;

    // Count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(), bind2nd(less<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 greater than 5 is: 4.
The number of elements in v1 less than 10 is: 2.
```

## <a name="bind2nd"></a>  bind2nd

Вспомогательная функция шаблона, которая создает адаптер для преобразования объекта бинарной функции в объект унарной функции, привязывая второй аргумент бинарной функции к указанному значению.

```cpp
template <class Operation, class Type>
binder2nd <Operation> bind2nd(const Operation& func, const Type& right);
```

### <a name="parameters"></a>Параметры

`func` Объект бинарной функции для преобразования в объект унарной функции.

`right` Значение, к которому привязан второй аргумент бинарной функции объекта.

### <a name="return-value"></a>Возвращаемое значение

Объект функции унарный, полученный в результате привязывая второй аргумент бинарной функции объекта значение `right`.

### <a name="remarks"></a>Примечания

Модули привязки функций — это разновидность адаптера функций. Так как они возвращают объекты функций, их можно использовать в композициях функций некоторого типа для создания более сложных и мощных выражений.

Если `func` — объект типа **Operation**, а `c` — константа, то `bind2nd` ( `func`, `c` ) эквивалентен [binder2nd](../standard-library/binder2nd-class.md) конструктора класса **binder2nd\<Operation>** ( `func`, `c` ) и является более удобным.

### <a name="example"></a>Пример

```cpp
// functional_bind2nd.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

// Creation of a user-defined function object
// that inherits from the unary_function base class
class greaterthan15: unary_function<int, bool>
{
public:
    result_type operator()(argument_type i)
    {
        return (result_type)(i > 15);
    }
};

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1a;
    result1a = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1a << "." << endl;

    // Compare counting the number of integers > 15 in the vector
    // with a user-defined function object
    vector<int>::iterator::difference_type result1b;
    result1b = count_if(v1.begin(), v1.end(), greaterthan15());
    cout << "The number of elements in v1 greater than 15 is: "
         << result1b << "." << endl;

    // Count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(), bind1st(greater<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 greater than 15 is: 2.
The number of elements in v1 less than 10 is: 2.
```

## <a name="bit_and"></a>  bit_and

Стандартный объект функции, который выполняет над своими аргументами побитовую операцию И (бинарная `operator&`).

```cpp
template <class Type = void>
struct bit_and : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
 };

// specialized transparent functor for operator&
template <>
struct bit_and<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const  ->
        decltype(std::forward<T>(Left) & std::forward<U>(Right));
};
```

### <a name="parameters"></a>Параметры

`Type`, `T`, `U` Любой тип, поддерживающий `operator&` , принимающий операнды указанного или выводимого типа.

`Left` Левый операнд побитовой операции и. Неспециализированный шаблон принимает ссылочный аргумент lvalue типа `Type`. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue выводимого типа `T`.

`Right` Правый операнд побитовой операции и. Неспециализированный шаблон принимает ссылочный аргумент lvalue типа `Type`. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue выводимого типа `U`.

### <a name="return-value"></a>Возвращаемое значение

Результат `Left & Right`. Специализированный шаблон выполняет точную пересылку результата типа, возвращаемого `operator&`.

### <a name="remarks"></a>Примечания

Функтор `bit_and` ограничен целочисленными типами для основных типов данных или определяемыми пользователем типами, которые реализуют бинарную `operator&`.

## <a name="bit_not"></a>  bit_not

Стандартный объект функции, который выполняет над своими аргументами операцию побитового дополнения (НЕ) (бинарная `operator~`).

```cpp
template <class Type = void>
struct bit_not : public unary_function<Type, Type>
 {
    Type operator()(const Type& Right) const;
 };

// specialized transparent functor for operator~
template <>
struct bit_not<void>
 {
    template <class Type>
    auto operator()(Type&& Right) const  ->  decltype(~std::forward<Type>(Right));
 };
```

### <a name="parameters"></a>Параметры

`Type` Тип, поддерживающий унарный `operator~`.

`Right` Операнд побитовую операцию дополнения. Неспециализированный шаблон принимает ссылочный аргумент lvalue типа `Type`. Специализированный шаблон выполняет точную пересылку значения lvalue или ссылочного аргумента rvalue выводимого типа `Type`.

### <a name="return-value"></a>Возвращаемое значение

Результат `~ Right`. Специализированный шаблон выполняет точную пересылку результата типа, возвращаемого `operator~`.

### <a name="remarks"></a>Примечания

Функтор `bit_not` ограничен целочисленными типами для основных типов данных или определяемыми пользователем типами, которые реализуют бинарную `operator~`.

## <a name="bit_or"></a>  bit_or

Стандартный объект функции, который применяет побитовую операцию ИЛИ (`operator|`) к своим аргументам.

```cpp
template <class Type = void>
struct bit_or : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
 };

// specialized transparent functor for operator|
template <>
struct bit_or<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
        ->  decltype(std::forward<T>(Left) | std::forward<U>(Right));
};
```

### <a name="parameters"></a>Параметры

`Type`, `T`, `U` Любой тип, поддерживающий `operator|` , принимающий операнды указанного или выводимого типа.

`Left` Левый операнд побитовой операции или. Неспециализированный шаблон принимает ссылочный аргумент lvalue типа `Type`. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue выводимого типа `T`.

`Right` Правый операнд побитовой операции или. Неспециализированный шаблон принимает ссылочный аргумент lvalue типа `Type`. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue выводимого типа `U`.

### <a name="return-value"></a>Возвращаемое значение

Результат `Left | Right`. Специализированный шаблон выполняет точную пересылку результата типа, возвращаемого `operator|`.

### <a name="remarks"></a>Примечания

Функтор `bit_or` ограничен целочисленными типами для основных типов данных или определяемыми пользователем типами, которые реализуют `operator|`.

## <a name="bit_xor"></a>  bit_xor

Стандартный объект функции, который применяет побитовую операцию "исключающее ИЛИ" (бинарное `operator^`) к своим аргументам.

```cpp
template <class Type = void>
struct bit_xor : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
 };

// specialized transparent functor for operator^
template <>
struct bit_xor<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
        -> decltype(std::forward<T>(Left) ^ std::forward<U>(Right));
};
```

### <a name="parameters"></a>Параметры

`Type`, `T`, `U` Любой тип, поддерживающий `operator^` , принимающий операнды указанного или выводимого типа.

`Left` Левый операнд побитовой операции XOR. Неспециализированный шаблон принимает ссылочный аргумент lvalue типа `Type`. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue выводимого типа `T`.

`Right` Правый операнд побитовой операции XOR. Неспециализированный шаблон принимает ссылочный аргумент lvalue типа `Type`. Специализированный шаблон выполняет точную пересылку ссылочных аргументов lvalue и rvalue выводимого типа `U`.

### <a name="return-value"></a>Возвращаемое значение

Результат `Left ^ Right`. Специализированный шаблон выполняет точную пересылку результата типа, возвращаемого `operator^`.

### <a name="remarks"></a>Примечания

Функтор `bit_xor` ограничен целочисленными типами для основных типов данных или определяемыми пользователем типами, которые реализуют бинарную `operator^`.

## <a name="cref"></a>  cref

Создает конструкцию `reference_wrapper` из аргумента.

```cpp
template <class Ty>
reference_wrapper<const Ty> cref(const Ty& arg);

template <class Ty>
reference_wrapper<const Ty> cref(const reference_wrapper<Ty>& arg);
```

### <a name="parameters"></a>Параметры

`Ty` Тип аргумента для упаковки.

`arg` Аргумент для создания оболочки.

### <a name="remarks"></a>Примечания

Первая функция возвращает `reference_wrapper<const Ty>(arg.get())`. Используется для создания оболочки для константной ссылки. Вторая функция возвращает `reference_wrapper<const Ty>(arg)`. Используется для восстановления константной ссылки из ссылки в оболочке.

### <a name="example"></a>Пример

```cpp
// std__functional__cref.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    int i = 1;

    std::cout << "i = " << i << std::endl;
    std::cout << "cref(i) = " << std::cref(i) << std::endl;
    std::cout << "cref(neg)(i) = "
        << std::cref(&neg)(i) << std::endl;

    return (0);
    }

```

```Output
i = 1
cref(i) = 1
cref(neg)(i) = -1
```

## <a name="mem_fn"></a>  mem_fn

Создает простую оболочку вызова.

```cpp
template <class Ret, class Ty>
unspecified mem_fn(Ret Ty::*pm);
```

### <a name="parameters"></a>Параметры

`Ret` Возвращаемый тип в оболочку функция.

`Ty` Тип указателя на функцию члена.

### <a name="remarks"></a>Примечания

Шаблонная функция возвращает простую оболочку вызова `cw` со слабым типом результата, чтобы выражение `cw(t, a2, ..., aN)` было эквивалентно `INVOKE(pm, t, a2, ..., aN)`. Она не вызывает исключения.

Возвращаемая оболочка вызова является производной от `std::unary_function<cv Ty*, Ret>` (поэтому вложенный тип `result_type` определяется как синоним `Ret`, а вложенный тип `argument_type` — как синоним `cv Ty*`) только тогда, если тип `Ty` является указателем на функцию-член с CV-квалификатором `cv`, не принимающим аргументы.

Возвращаемая оболочка вызова является производной от `std::binary_function<cv Ty*, T2, Ret>` (поэтому вложенный тип `result_type` определяется как синоним `Ret`, вложенный тип `first argument_type` — как синоним `cv Ty*`, а вложенный тип `second argument_type` — как синоним `T2`) только тогда, если тип `Ty` является указателем на функцию-член с CV-квалификатором `cv`, принимающим один аргумент типа `T2`.

### <a name="example"></a>Пример

```cpp
// std__functional__mem_fn.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

class Funs
    {
public:
    void square(double x)
        {
        std::cout << x << "^2 == " << x * x << std::endl;
        }

    void product(double x, double y)
        {
        std::cout << x << "*" << y << " == " << x * y << std::endl;
        }
    };

int main()
    {
    Funs funs;

    std::mem_fn(&Funs::square)(funs, 3.0);
    std::mem_fn(&Funs::product)(funs, 3.0, 2.0);

    return (0);
    }

```

```Output
3^2 == 9
3*2 == 6
```

## <a name="mem_fun"></a>  mem_fun

Вспомогательные функции шаблона, которые используются для создания адаптеров объекта-функции для функций-членов при инициализации с аргументами указателя.

```cpp
template <class Result, class Type>
mem_fun_t<Result, Type> mem_fun (Result(Type::* pmem)());

template <class Result, class Type, class Arg>
mem_fun1_t<Result, Type, Arg> mem_fun(Result (Type::* pmem)(Arg));

template <class Result, class Type>
const_mem_fun_t<Result, Type> mem_fun(Result (Type::* pmem)() const);

template <class Result, class Type, class Arg>
const_mem_fun1_t<Result, Type, Arg> mem_fun(Result (Type::* pmem)(Arg) const);
```

### <a name="parameters"></a>Параметры

`pmem` Указатель на функцию-член класса **типа** для преобразования в объект функции.

### <a name="return-value"></a>Возвращаемое значение

Объект функции **const** или **non_const** типа `mem_fun_t` или `mem_fun1_t`.

### <a name="example"></a>Пример

```cpp
// functional_mem_fun.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

class StoreVals
{
    int val;
public:
    StoreVals() { val = 0; }
    StoreVals(int j) { val = j; }

    bool display() { cout << val << " "; return true; }
    int squareval() { val *= val; return val; }
    int lessconst(int k) {val -= k; return val; }
};

int main( )
{
    vector<StoreVals *> v1;

    StoreVals sv1(5);
    v1.push_back(&sv1);
    StoreVals sv2(10);
    v1.push_back(&sv2);
    StoreVals sv3(15);
    v1.push_back(&sv3);
    StoreVals sv4(20);
    v1.push_back(&sv4);
    StoreVals sv5(25);
    v1.push_back(&sv5);

    cout << "The original values stored are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;

    // Use of mem_fun calling member function through a pointer
    // square each value in the vector using squareval ()
    for_each(v1.begin(), v1.end(), mem_fun<int, StoreVals>(&StoreVals::squareval));
    cout << "The squared values are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;

    // Use of mem_fun1 calling member function through a pointer
    // subtract 5 from each value in the vector using lessconst ()
    for_each(v1.begin(), v1.end(),
        bind2nd (mem_fun1<int, StoreVals,int>(&StoreVals::lessconst), 5));
    cout << "The squared values less 5 are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;
}
```

## <a name="mem_fun_ref"></a>  mem_fun_ref

Вспомогательные функции шаблона, которые используются для создания адаптеров объекта-функции для функций-членов при инициализации с помощью ссылочных аргументов.

```cpp
template <class Result, class Type>
mem_fun_ref_t<Result, Type> mem_fun_ref(Result (Type::* pmem)());

template <class Result, class Type, class Arg>
mem_fun1_ref_t<Result, Type, Arg> mem_fun_ref(Result (Type::* pmem)(Arg));

template <class Result, class Type>
const_mem_fun_ref_t<Result, Type> mem_fun_ref(Result Type::* pmem)() const);

template <class Result, class Type, class Arg>
const_mem_fun1_ref_t<Result, Type, Arg> mem_fun_ref(Result (T::* pmem)(Arg) const);
```

### <a name="parameters"></a>Параметры

`pmem` Указатель на функцию-член класса `Type` для преобразования в объект функции.

### <a name="return-value"></a>Возвращаемое значение

Объект функции `const` или `non_const` типа `mem_fun_ref_t` или `mem_fun1_ref_t`.

### <a name="example"></a>Пример

```cpp
// functional_mem_fun_ref.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

class NumVals
   {
   int val;
   public:
   NumVals ( ) { val = 0; }
   NumVals ( int j ) { val = j; }

   bool display ( ) { cout << val << " "; return true; }
   bool isEven ( ) { return ( bool )  !( val %2 ); }
   bool isPrime( )
   {
      if (val < 2) { return true; }
      for (int i = 2; i <= val / i; ++i)
      {
         if (val % i == 0) { return false; }
      }
      return true;
   }
};

int main( )
{
   vector <NumVals> v1 ( 13 ), v2 ( 13 );
   vector <NumVals>::iterator v1_Iter, v2_Iter;
   int i, k;

   for ( i = 0; i < 13; i++ ) v1 [ i ] = NumVals ( i+1 );
   for ( k = 0; k < 13; k++ ) v2 [ k ] = NumVals ( k+1 );

   cout << "The original values stored in v1 are: " ;
   for_each( v1.begin( ), v1.end( ),
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   // Use of mem_fun_ref calling member function through a reference
   // remove the primes in the vector using isPrime ( )
   v1_Iter = remove_if ( v1.begin( ),  v1.end( ),
      mem_fun_ref ( &NumVals::isPrime ) );
   cout << "With the primes removed, the remaining values in v1 are: " ;
   for_each( v1.begin( ), v1_Iter,
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   cout << "The original values stored in v2 are: " ;
   for_each( v2.begin( ), v2.end( ),
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   // Use of mem_fun_ref calling member function through a reference
   // remove the even numbers in the vector v2 using isEven ( )
   v2_Iter = remove_if ( v2.begin( ),  v2.end( ),
      mem_fun_ref ( &NumVals::isEven ) );
   cout << "With the even numbers removed, the remaining values are: " ;
   for_each( v2.begin( ),  v2_Iter,
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;
}
```

```Output
The original values stored in v1 are: 1 2 3 4 5 6 7 8 9 10 11 12 13
With the primes removed, the remaining values in v1 are: 4 6 8 9 10 12
The original values stored in v2 are: 1 2 3 4 5 6 7 8 9 10 11 12 13
With the even numbers removed, the remaining values are: 1 3 5 7 9 11 13
```

## <a name="not1"></a>  not1

Возвращает дополнение унарного предиката.

```cpp
template <class UnaryPredicate>
unary_negate<UnaryPredicate> not1(const UnaryPredicate& pred);
```

### <a name="parameters"></a>Параметры

`pred` Унарный предикат, который должен быть инвертирован.

### <a name="return-value"></a>Возвращаемое значение

Унарный предикат, который является отрицанием измененного унарного предиката.

### <a name="remarks"></a>Примечания

Если `unary_negate` создан на основе унарного предиката **Pred**( *x*), то он возвращает **!Pred**( *x*).

### <a name="example"></a>Пример

```cpp
// functional_not1.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 7; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    // Count the elements greater than 10
    result1 = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    vector<int>::iterator::difference_type result2;
    // Use the negator to count the elements less than or equal to 10
    result2 = count_if(v1.begin(), v1.end(),
        not1(bind2nd(greater<int>(), 10)));

    cout << "The number of elements in v1 not greater than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 30 35 )
The number of elements in v1 greater than 10 is: 5.
The number of elements in v1 not greater than 10 is: 3.
```

## <a name="not2"></a>  not2

Возвращает дополнение бинарного предиката.

```cpp
template <class BinaryPredicate>
binary_negate<BinaryPredicate> not2(const BinaryPredicate& func);
```

### <a name="parameters"></a>Параметры

`func` Двоичный предикат, который должен быть инвертирован.

### <a name="return-value"></a>Возвращаемое значение

Бинарный предикат, который является отрицанием измененного бинарного предиката.

### <a name="remarks"></a>Примечания

Если `binary_negate` создан на основе бинарного предиката **BinPred**( *x*, *y*), то он возвращает ! **BinPred**( *x*, *y*).

### <a name="example"></a>Пример

```cpp
// functional_not2.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <cstdlib>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   v1.push_back( 6262 );
   v1.push_back( 6262 );
   for ( i = 0 ; i < 5 ; i++ )
   {
      v1.push_back( rand( ) );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   // use default binary predicate less<int>( )
   sort( v1.begin( ), v1.end( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order,
   // use the binary_negate helper function not2
   sort( v1.begin( ), v1.end( ), not2(less<int>( ) ) );
   cout << "Resorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = ( 6262 6262 41 18467 6334 26500 19169 )
Sorted vector v1 = ( 41 6262 6262 6334 18467 19169 26500 )
Resorted vector v1 = ( 26500 19169 18467 6334 6262 6262 41 )
```

## <a name="ptr_fun"></a>  ptr_fun

Вспомогательные функции шаблона, которые используются для преобразования указателей на унарные и бинарные функции соответственно в унарные и бинарные адаптируемые функции.

```cpp
template <class Arg, class Result>
pointer_to_unary_function<Arg, Result, Result (*)(Arg)> ptr_fun(Result (*pfunc)(Arg));

template <class Arg1, class Arg2, class Result>
pointer_to_binary_function<Arg1, Arg2, Result, Result (*)(Arg1, Arg2)> ptr_fun(Result (*pfunc)(Arg1, Arg2));
```

### <a name="parameters"></a>Параметры

`pfunc` Унарным или бинарным указатель на функцию для преобразования адаптируемые функции.

### <a name="return-value"></a>Возвращаемое значение

Первая функция шаблон возвращает унарную функцию [pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md) < `Arg`, **Result**>(* `pfunc`).

Вторая функция шаблон возвращает бинарную функцию [pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md) \< **Arg1**, **Arg2**, **Result**>(* `pfunc`).

### <a name="remarks"></a>Примечания

Указатель на функцию является объектом функции и может передаваться в любой алгоритм стандартной библиотеки C++, ожидающий унарную функцию в качестве параметра, но не является адаптируемым. Для использования его с адаптером, например привязка к нему значения или использование его с инвертором, он должен передаваться с вложенными типами, что делает возможной такую адаптацию. Преобразование указателей на унарные и бинарные функции с помощью вспомогательной функции `ptr_fun` позволяет адаптерам функций работать с такими указателями.

### <a name="example"></a>Пример

[!code-cpp[functional_ptr_fun#1](../standard-library/codesnippet/CPP/functional-functions_1.cpp)]

## <a name="ref"></a>  ref

Создает `reference_wrapper` из аргумента.

```cpp
template <class Ty>
reference_wrapper<Ty> ref(Ty& arg);

template <class Ty>
reference_wrapper<Ty> ref(reference_wrapper<Ty>& arg);
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на `arg`, а именно `reference_wrapper<Ty>(arg)`.

### <a name="example"></a>Пример

В приведенном ниже примере определяются две функции: одна из них привязана к строковой переменной, а другая — к ссылке строковой переменной, вычисленной с помощью вызова `ref`. Когда значение переменной меняется, первая функция продолжает использовать старое значение, а вторая использует новое значение.

```cpp
#include <algorithm>
#include <functional>
#include <iostream>
#include <iterator>
#include <ostream>
#include <string>
#include <vector>
using namespace std;
using namespace std;
using namespace std::placeholders;

bool shorter_than(const string& l, const string& r) {
    return l.size() < r.size();
}

int main() {
    vector<string> v_original;
    v_original.push_back("tiger");
    v_original.push_back("cat");
    v_original.push_back("lion");
    v_original.push_back("cougar");

    copy(v_original.begin(), v_original.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    string s("meow");

    function<bool (const string&)> f = bind(shorter_than, _1, s);
    function<bool (const string&)> f_ref = bind(shorter_than, _1, ref(s));

    vector<string> v;

    // Remove elements that are shorter than s ("meow")

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    // Now change the value of s.
    // f_ref, which is bound to ref(s), will use the
    // new value, while f is still bound to the old value.

    s = "kitty";

    // Remove elements that are shorter than "meow" (f is bound to old value of s)

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    // Remove elements that are shorter than "kitty" (f_ref is bound to ref(s))

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f_ref), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;
}
```

```Output
tiger cat lion cougar
tiger lion cougar
tiger lion cougar
tiger cougar
```

## <a name="swap"></a>  swap

Меняет местами два объекта `function`.

```cpp
template <class Fty>
void swap(function<Fty>& f1, function<Fty>& f2);
```

### <a name="parameters"></a>Параметры

`Fty` Тип, управляемый объекты функций.

`f1` Первый объект функции.

`f2` Второй объект функции.

### <a name="remarks"></a>Примечания

Функция возвращает `f1.swap(f2)`.

### <a name="example"></a>Пример

```cpp
// std__functional__swap.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0(neg);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << "val == " << fn0(3) << std::endl;

    std::function<int (int)> fn1;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << std::endl;

    swap(fn0, fn1);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    return (0);
    }

```

```Output
empty == false
val == -3
empty == true

empty == true
empty == false
val == -3
```

## <a name="see-also"></a>См. также

[\<functional>](../standard-library/functional.md)<br/>
