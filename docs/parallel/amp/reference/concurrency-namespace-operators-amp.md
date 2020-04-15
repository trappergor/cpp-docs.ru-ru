---
title: Операторы пространства имен Concurrency (AMP)
ms.date: 11/04/2016
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
ms.openlocfilehash: c4086029b71d71091a12b9b6023cc6098faf2f85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376292"
---
# <a name="concurrency-namespace-operators-amp"></a>Операторы пространства имен Concurrency (AMP)

||||
|-|-|-|
|[оператора!](#operator_neq)|[оператор%](#operator_mod)|[оператор](#operator_star)|
|[оператор](#operator_add)|[оператор-](#operator-)|[оператор/](#operator_div)|
|[оператора](#operator_eq_eq)|

## <a name="operator"></a><a name="operator_eq_eq"></a>оператора

Определяет, являются ли указанные аргументы равными.

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
Ранг аргументов tuple.

*_Lhs*<br/>
Один из заутронок для сравнения.

*_Rhs*<br/>
Один из заутронок для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если зауленые были равны; в противном случае, **ложные**.

## <a name="operator"></a><a name="operator_neq"></a>оператора!

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
Ранг аргументов tuple.

*_Lhs*<br/>
Один из заутронок для сравнения.

*_Rhs*<br/>
Один из заутронок для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если зазубра не равны; в противном случае, **ложные**.

## <a name="operator"></a><a name="operator_add"></a>оператор

Вычисляет компонентную сумму указанных аргументов.

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
Ранг аргументов tuple.

*_Lhs*<br/>
Один из аргументов, чтобы добавить.

*_Rhs*<br/>
Один из аргументов, чтобы добавить.

### <a name="return-value"></a>Возвращаемое значение

Сумма, предусмотренная компонентом, из указанных аргументов.

## <a name="operator-"></a><a name="operator-"></a>оператор-

Вычисляет разницу между указанными аргументами по компонентам.

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
Ранг аргументов tuple.

*_Lhs*<br/>
Аргумент, который следует вычесть.

*_Rhs*<br/>
Аргумент для вычитания.

### <a name="return-value"></a>Возвращаемое значение

Разница между указанными аргументами по компонентам.

## <a name="operator"></a><a name="operator_star"></a>оператор

Вычисляет компонентный продукт из указанных аргументов.

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
Ранг аргументов tuple.

*_Lhs*<br/>
Один из заутронок размножаться.

*_Rhs*<br/>
Один из заутронок размножаться.

### <a name="return-value"></a>Возвращаемое значение

Компонент-мудрый продукт указанных аргументов.

## <a name="operator"></a><a name="operator_div"></a>оператор/

Вычисляет компонентный коэффициент указанных аргументов.

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
Ранг аргументов tuple.

*_Lhs*<br/>
Туляки, которые должны быть разделены.

*_Rhs*<br/>
Туляки, чтобы разделить.

### <a name="return-value"></a>Возвращаемое значение

Компонент-мудрый коэффициент указанных аргументов.

## <a name="operator"></a><a name="operator_mod"></a>оператор%

Вычисляет модули первого указанного аргумента вторым указанным аргументом.

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
Ранг аргументов tuple.

*_Lhs*<br/>
Туляк, из которого рассчитывается модуло.

*_Rhs*<br/>
Туляк и модуло.

### <a name="return-value"></a>Возвращаемое значение

Результат первого указанного аргумента модульный второй указанный аргумент.

## <a name="see-also"></a>См. также раздел

[Пространство имен параллелизма](concurrency-namespace-cpp-amp.md)
