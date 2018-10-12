---
title: Операторы пространства имен Concurrency (AMP) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f1e313dbda3dfc75f291310818d593b9a4daf90b
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162182"
---
# <a name="concurrency-namespace-operators-amp"></a>Операторы пространства имен Concurrency (AMP)

||||
|-|-|-|
|[operator!=](#operator_neq)|[оператор%](#operator_mod)|[оператор*](#operator_star)|
|[operator+](#operator_add)|[operator-](#operator-)|[оператор/](#operator_div)|
|[operator==](#operator_eq_eq)|

##  <a name="operator_eq_eq"></a> operator==

Определяет, равны ли два заданных аргументов.

```
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
Один из кортежей для сравнения.

*_Rhs*<br/>
Один из кортежей для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если кортежи равны; в противном случае — значение **false**.

##  <a name="operator_neq"></a> operator!=

Определяет, равны ли указанные аргументы.

```
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
Один из кортежей для сравнения.

*_Rhs*<br/>
Один из кортежей для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если кортежи не равны; в противном случае — значение **false**.

##  <a name="operator_add"></a> operator+

Вычисляет покомпонентную сумму двух заданных аргументов.

```
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
Одно из добавляемых аргументов.

*_Rhs*<br/>
Одно из добавляемых аргументов.

### <a name="return-value"></a>Возвращаемое значение

Покомпонентную сумму двух заданных аргументов.

##  <a name="operator-"></a>  оператор-

Вычисляет разность между указанными аргументами.

```
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
Аргумент для вычитания из.

*_Rhs*<br/>
Аргумент для вычитания.

### <a name="return-value"></a>Возвращаемое значение

Разность между указанными аргументами.

##  <a name="operator_star"></a>  оператор*

Вычисляет покомпонентное произведение заданных аргументов.

```
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
Один из кортежей для умножения.

*_Rhs*<br/>
Один из кортежей для умножения.

### <a name="return-value"></a>Возвращаемое значение

Покомпонентное произведение заданных аргументов.

##  <a name="operator_div"></a>  оператор/

Вычисляет покомпонентное частное двух заданных аргументов.

```
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
Кортеж, которое необходимо разделить.

*_Rhs*<br/>
Кортеж, который необходимо разделить.

### <a name="return-value"></a>Возвращаемое значение

Покомпонентное частное двух заданных аргументов.

##  <a name="operator_mod"></a>  оператор%

Вычисляет остаток деления первого заданного аргумента с помощью второго заданного аргумента.

```
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
Кортеж остаток от деления по.

### <a name="return-value"></a>Возвращаемое значение

Результат первого заданного аргумента модуля второго заданного аргумента.

## <a name="see-also"></a>См. также

[пространство имен Concurrency ](concurrency-namespace-cpp-amp.md)
