---
title: Операторы &lt;chrono&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- chrono/std::operator modulo
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
ms.openlocfilehash: 56a8d05c3a68cf8d3e12b8a6452d43033e414cbf
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102724"
---
# <a name="ltchronogt-operators"></a>Операторы &lt;chrono&gt;

||||
|-|-|-|
|[operator modulo](#op_modulo)|[оператор!=](#op_neq)|[оператор&gt;](#op_gt)|
|[operator&gt;=](#op_gt_eq)|[оператор&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|
|[оператор*](#op_star)|[operator+](#op_add)|[operator-](#operator-)|
|[оператор/](#op_div)|[оператор==](#op_eq_eq)|

## <a name="operator-"></a>  operator-

Оператор вычитания или отрицания объектов [duration](../standard-library/duration-class.md) и [time_point](../standard-library/time-point-class.md).

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type
   operator-(
       const duration<Rep1, Period1>& Left,
       cconst duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Rep2, class Period2>
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type
   operator-(
       const time_point<Clock, Duration1>& Time,
       const duration<Rep2, Period2>& Dur);


template <class Clock, class Duration1, class Duration2>
constexpr typename common_type<Duration1, Duration2>::type
   operator-(
       const time_point<Clock, Duration1>& Left,
       const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

*Слева*<br/>
Левый объект `duration` или объект `time_point`.

*Справа*<br/>
Правый объект `duration` или объект `time_point`.

*Время*<br/>
Объект `time_point`.

*Длительность*<br/>
Объект `duration`.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает объект `duration`, длительность интервала которого равна разнице временных интервалов двух аргументов.

Вторая функция возвращает `time_point` , представляющий точку во времени, отстоящий отрицание временного интервала, представленного *Dur*, от момента времени, который задается параметром *время*.

Третья функция возвращает `duration` , представляющий интервал времени между *слева* и *справа*.

## <a name="op_neq"></a> operator!=

Оператор неравенства для объектов [duration](../standard-library/duration-class.md) и [time_point](../standard-library/time-point-class.md).

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator!=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);


template <class Clock, class Duration1, class Duration2>
constexpr bool operator!=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

*Слева*<br/>
Левый объект `duration` или объект `time_point`.

*Справа*<br/>
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `!(Left == Right)`.

## <a name="op_star"></a>  operator*

Оператор деления для объектов [duration](../standard-library/chrono-operators.md#op_star).

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1>
   operator*(
      const duration<Rep1, Period1>& Dur,
      const Rep2& Mult);


template <class Rep1, class Rep2, class Period2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period2>
   operator*(
       const Rep1& Mult,
       const duration<Rep2,
       Period2>& Dur);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Объект `duration`.

*Mult*<br/>
Целочисленное значение.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает `duration` объекта, длительность интервала которого равна *Mult* умноженное на длину *Dur*.

Если `is_convertible<Rep2, common_type<Rep1, Rep2>>`*содержит значение true*, первая функция не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

Если `is_convertible<Rep1, common_type<Rep1, Rep2>>`*не содержит значение true*, вторая функция не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

## <a name="op_div"></a>  operator/

Оператор деления для объектов[duration](../standard-library/chrono-operators.md#op_star).

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1>
   operator/(
     const duration<Rep1, Period1>& Dur,
     const Rep2& Div);


template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<Rep1, Rep2>::type
   operator/(
     const duration<Rep1, Period1>& Left,
     const duration<Rep2, Period2>& Right);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Объект `duration`.

*ДИВ*<br/>
Целочисленное значение.

*Слева*<br/>
Левый объект `duration`.

*Справа*<br/>
Правой объект `duration`.

### <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает объект длительность интервала которого длина равна длине *Dur* деленной на значение *Div*.

Второй оператор возвращает соотношение длительностей интервалов из *слева* и *справа*.

Если `is_convertible<Rep2, common_type<Rep1, Rep2>>`*содержит значение true*, а `Rep2` не является экземпляром `duration`, первый оператор не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

## <a name="op_add"></a>  operator+

Добавляет объекты [duration](../standard-library/duration-class.md) и [time_point](../standard-library/time-point-class.md).

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type
   operator+(
      const duration<Rep1, Period1>& Left,
      const duration<Rep2, Period2>& Right);


template <class Clock, class Duration1, class Rep2, class Period2>
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type>
   operator+(
      const time_point<Clock, Duration1>& Time,
      const duration<Rep2, Period2>& Dur);


template <class Rep1, class Period1, class Clock, class Duration2>
time_point<Clock, constexpr typename common_type<duration<Rep1, Period1>, Duration2>::type>
   operator+(
      const duration<Rep1, Period1>& Dur,
      const time_point<Clock, Duration2>& Time);
```

### <a name="parameters"></a>Параметры

*Слева*<br/>
Левый объект `duration` или объект `time_point`.

*Справа*<br/>
Правый объект `duration` или объект `time_point`.

*Время*<br/>
Объект `time_point`.

*Длительность*<br/>
Объект `duration`.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает `duration` объект, с временным интервалом, равным сумме интервалов *слева* и *справа*.

Вторая и третья функции возвращают `time_point` , представляющий точку во времени, отстоящий интервал *Dur*, от момента времени *время*.

## <a name="op_lt"></a> operator&lt;

Определяет, справедливо ли, что один из объектов [duration](../standard-library/duration-class.md) или [time_point](../standard-library/time-point-class.md) меньше, чем другой объект `duration` или `time_point`.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator<(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);


template <class Clock, class Duration1, class Duration2>
constexpr bool operator<(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

*Слева*<br/>
Левый объект `duration` или объект `time_point`.

*Справа*<br/>
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает **true** Если длина интервала *слева* меньше, чем длина интервала *справа*. В противном случае функция возвращает **false**.

Вторая функция возвращает **true** Если *слева* предшествует *справа*. В противном случае функция возвращает **false**.

## <a name="op_lt_eq"></a> operator&lt;=

Определяет, верно ли, что один из объектов [duration](../standard-library/duration-class.md) или [time_point](../standard-library/time-point-class.md) меньше другого объекта `duration` или `time_point` или равен ему.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator<=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator<=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

*Слева*<br/>
Левый объект `duration` или объект `time_point`.

*Справа*<br/>
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `!(Right < Left)`.

## <a name="op_eq_eq"></a> operator==

Определяет, справедливо ли, что два объекта `duration` представляют интервалы времени, имеющие одинаковую длину, или, что два объекта `time_point` представляют один и тот же момент времени.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator==(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator==(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

*Слева*<br/>
Левый объект `duration` или объект `time_point`.

*Справа*<br/>
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает **true** Если *слева* и *справа* представляют интервалы времени, которые имеют одинаковую длину. В противном случае функция возвращает **false**.

Вторая функция возвращает **true** Если *слева* и *справа* представляют тот же момент времени. В противном случае функция возвращает **false**.

## <a name="op_gt"></a> operator&gt;

Определяет, верно ли, что один из объектов [duration](../standard-library/duration-class.md) или [time_point](../standard-library/time-point-class.md) больше, чем другой объект `duration` или `time_point`.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator>(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator>(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

*Слева*<br/>
Левый объект `duration` или объект `time_point`.

*Справа*<br/>
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `Right < Left`.

## <a name="op_gt_eq"></a> operator&gt;=

Определяет, верно ли, что один из объектов [duration](../standard-library/duration-class.md) или [time_point](../standard-library/time-point-class.md) больше другого объекта `duration` или `time_point` или равен ему.

```cpp
template <class Rep1, class Period1, class Rep2, class Period2>
constexpr bool operator>=(
    const duration<Rep1, Period1>& Left,
    const duration<Rep2, Period2>& Right);

template <class Clock, class Duration1, class Duration2>
constexpr bool operator>=(
    const time_point<Clock, Duration1>& Left,
    const time_point<Clock, Duration2>& Right);
```

### <a name="parameters"></a>Параметры

*Слева*<br/>
Левый объект `duration` или объект `time_point`.

*Справа*<br/>
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `!(Left < Right)`.

## <a name="op_modulo"></a>  operator modulo

Оператор для операций вычисления остатка от деления над объектами [duration](../standard-library/duration-class.md).

```cpp
template <class Rep1, class Period1, class Rep2>
constexpr duration<Rep1, Period1, Rep2>::type
   operator%(
      const duration<Rep1, Period1>& Dur,
      const Rep2& Div);

template <class Rep1, class Period1, class Rep2, class Period2>
constexpr typename common_type<duration<Rep1, _Period1>, duration<Rep2, Period2>>::type
   operator%(
     const duration<Rep1, Period1>& Left,
     const duration<Rep2, Period2>& Right);
```

### <a name="parameters"></a>Параметры

*Длительность*<br/>
Объект `duration`.

*ДИВ*<br/>
Целочисленное значение.

*Слева*<br/>
Левый объект `duration`.

*Справа*<br/>
Правой объект `duration`.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает `duration` объекта, длительность интервала которого равна *Dur* остаток от деления *Div*.

Вторая функция возвращает значение, представляющее *слева* остаток от деления *справа*.

## <a name="see-also"></a>См. также

[\<chrono>](../standard-library/chrono.md)<br/>
