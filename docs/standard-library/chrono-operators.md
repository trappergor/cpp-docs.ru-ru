---
title: Операторы &lt;chrono&gt;
ms.date: 11/04/2016
f1_keywords:
- chrono/std::operator modulo
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
ms.openlocfilehash: 398e2429c38cffb454c7b510aa5ab44fbe4cfef6
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865208"
---
# <a name="ltchronogt-operators"></a>Операторы &lt;chrono&gt;

## <a name="operator-"></a>станции

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

*Left*\
Левый объект `duration` или объект `time_point`.

*Справа*\
Правый объект `duration` или объект `time_point`.

*Время*\
Объект `time_point` .

*Длительность*\
Объект `duration` .

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает объект `duration`, длительность интервала которого равна разнице временных интервалов двух аргументов.

Вторая функция возвращает `time_point` объект, представляющий момент времени, который отменяется, путем отрицания интервала времени, представленного в параметре *длит*, с момента времени, заданного параметром *time*.

Третья функция возвращает `duration` объект, представляющий интервал времени между *левым* и *правым*.

## <a name="op_neq"></a>operator! =

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

*Left*\
Левый объект `duration` или объект `time_point`.

*Справа*\
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `!(Left == Right)`.

## <a name="op_star"></a>станции

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

*Длительность*\
Объект `duration` .

*Mult*\
Целочисленное значение.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает объект `duration`, длина интервала которого равна *mult* умножению на длину *длит*.

Если `is_convertible<Rep2, common_type<Rep1, Rep2>>`*содержит значение true*, первая функция не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

Если `is_convertible<Rep1, common_type<Rep1, Rep2>>`*не содержит значение true*, вторая функция не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

## <a name="op_div"></a>станции

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

*Длительность*\
Объект `duration` .

\ *div*
Целочисленное значение.

*Left*\
Левый объект `duration`.

*Справа*\
Правой объект `duration`.

### <a name="return-value"></a>Возвращаемое значение

Первый оператор возвращает объект Duration, длина интервала которого равна длительности *, деленной на* значение *div*.

Второй оператор возвращает отношение длины интервалов *влево* и *вправо*.

Если `is_convertible<Rep2, common_type<Rep1, Rep2>>`*содержит значение true*, а `Rep2` не является экземпляром `duration`, первый оператор не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

## <a name="op_add"></a>operator +

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

*Left*\
Левый объект `duration` или объект `time_point`.

*Справа*\
Правый объект `duration` или объект `time_point`.

*Время*\
Объект `time_point` .

*Длительность*\
Объект `duration` .

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает объект `duration` с интервалом времени, равным сумме интервалов *слева* и *справа*.

Вторая и третья функции возвращают объект `time_point`, представляющий точку во времени, которая отменяется с интервалом в *длит*, *с момента времени.*

## <a name="op_lt">Оператор </a>&lt;

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

*Left*\
Левый объект `duration` или объект `time_point`.

*Справа*\
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает **значение true** , если длина интервала *Left* меньше, чем длина интервала *справа*. В противном случае функция возвращает **значение false**.

Вторая функция возвращает **значение true** , если *слева* направо *.* В противном случае функция возвращает **значение false**.

## <a name="op_lt_eq"></a>&lt;оператора =

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

*Left*\
Левый объект `duration` или объект `time_point`.

*Справа*\
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `!(Right < Left)`.

## <a name="op_eq_eq"></a>Оператор = =

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

*Left*\
Левый объект `duration` или объект `time_point`.

*Справа*\
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает **значение true** , если *Left* и *right* представляют интервалы времени, имеющие одинаковую длину. В противном случае функция возвращает **значение false**.

Вторая функция возвращает **значение true** , если *Left* и *right* представляют один и тот же момент времени. В противном случае функция возвращает **значение false**.

## <a name="op_gt">Оператор </a>&gt;

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

*Left*\
Левый объект `duration` или объект `time_point`.

*Справа*\
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `Right < Left`.

## <a name="op_gt_eq"></a>&gt;оператора =

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

*Left*\
Левый объект `duration` или объект `time_point`.

*Справа*\
Правый объект `duration` или объект `time_point`.

### <a name="return-value"></a>Возвращаемое значение

Каждая функция возвращает значение `!(Left < Right)`.

## <a name="op_modulo"></a>оператор остатка от деления

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

*Длительность*\
Объект `duration` .

\ *div*
Целочисленное значение.

*Left*\
Левый объект `duration`.

*Справа*\
Правой объект `duration`.

### <a name="return-value"></a>Возвращаемое значение

Первая функция возвращает объект `duration`, длина интервала *которого равна мере по* модулю *div*.

Вторая функция возвращает значение, представляющее *левый* остаток *от*деления.
