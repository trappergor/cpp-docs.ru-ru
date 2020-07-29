---
title: Операторы пространства имен Concurrency (AMP)
ms.date: 11/04/2016
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
ms.openlocfilehash: 03079f8899f3b13c8509e1affd10a82191b1817c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228483"
---
# <a name="concurrency-namespace-operators-amp"></a>Операторы пространства имен Concurrency (AMP)

||||
|-|-|-|
|[operator! =](#operator_neq)|[станции](#operator_mod)|[станции](#operator_star)|
|[operator +](#operator_add)|[станции](#operator-)|[станции](#operator_div)|
|[Оператор = =](#operator_eq_eq)|

## <a name="operator"></a><a name="operator_eq_eq"></a>Оператор = =

Определяет, равны ли указанные аргументы.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
bool operator== (
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Rank*<br/>
Ранг аргументов кортежа.

*_Lhs*<br/>
Один из сравниваемых кортежей.

*_Rhs*<br/>
Один из сравниваемых кортежей.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если кортежи равны; в противном случае — **`false`** .

## <a name="operator"></a><a name="operator_neq"></a>operator! =

Определяет, являются ли указанные аргументы неравными.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
bool operator!= (
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```

### <a name="parameters"></a>Параметры

*_Rank*<br/>
Ранг аргументов кортежа.

*_Lhs*<br/>
Один из сравниваемых кортежей.

*_Rhs*<br/>
Один из сравниваемых кортежей.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если кортежи не равны; в противном случае — **`false`** .

## <a name="operator"></a><a name="operator_add"></a>operator +

Вычисляет покомпонентную сумму указанных аргументов.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rank*<br/>
Ранг аргументов кортежа.

*_Lhs*<br/>
Один из добавляемых аргументов.

*_Rhs*<br/>
Один из добавляемых аргументов.

### <a name="return-value"></a>Возвращаемое значение

Покомпонентная сумма указанных аргументов.

## <a name="operator-"></a><a name="operator-"></a>станции

Выполняет покомпонентное различие между заданными аргументами.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator-(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rank*<br/>
Ранг аргументов кортежа.

*_Lhs*<br/>
Аргумент, из которого вычитается значение.

*_Rhs*<br/>
Аргумент для вычитания.

### <a name="return-value"></a>Возвращаемое значение

Покомпонентная разница между заданными аргументами.

## <a name="operator"></a><a name="operator_star"></a>станции

Выполняет покомпонентное произведение заданных аргументов.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator*(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator*(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp, cpu);
```

### <a name="parameters"></a>Параметры

*_Rank*<br/>
Ранг аргументов кортежа.

*_Lhs*<br/>
Один из кортежей для перемножения.

*_Rhs*<br/>
Один из кортежей для перемножения.

### <a name="return-value"></a>Возвращаемое значение

Покомпонентное произведение заданных аргументов.

## <a name="operator"></a><a name="operator_div"></a>станции

Выполняет покомпонентное частное от указанных аргументов.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator/(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator/(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rank*<br/>
Ранг аргументов кортежа.

*_Lhs*<br/>
Кортеж, который необходимо разделить.

*_Rhs*<br/>
Кортеж, по которому производится деление.

### <a name="return-value"></a>Возвращаемое значение

Покомпонентное частное от указанных аргументов.

## <a name="operator"></a><a name="operator_mod"></a>станции

Выполняет вычисление остатка первого заданного аргумента по второму указанному аргументу.

```cpp
template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator%(
    const _Tuple_type<_Rank>& _Lhs,
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

template <
    int _Rank,
    template <int> class _Tuple_type
>
_Tuple_type<_Rank>   operator%(
    typename _Tuple_type<_Rank>::value_type _Lhs,
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Параметры

*_Rank*<br/>
Ранг аргументов кортежа.

*_Lhs*<br/>
Кортеж, из которого вычисляется остаток от деления.

*_Rhs*<br/>
Кортеж, по которому производится деление.

### <a name="return-value"></a>Возвращаемое значение

Результат первого указанного аргумента модуля, второго заданного аргумента.

## <a name="see-also"></a>См. также статью

[Пространство имен Concurrency](concurrency-namespace-cpp-amp.md)
