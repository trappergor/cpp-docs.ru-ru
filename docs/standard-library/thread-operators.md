---
title: Операторы &lt;thread&gt;
ms.date: 11/04/2016
f1_keywords:
- thread/std::operator!=
- thread/std::operator&gt;
- thread/std::operator&gt;=
- thread/std::operator&lt;
- thread/std::operator&lt;&lt;
- thread/std::operator&lt;=
- thread/std::operator==
ms.assetid: e6bb6c0f-64f9-4cb2-9ff2-05b88a6ba7ac
helpviewer_keywords:
- std::operator!= (thread)
- std::operator&gt; (thread)
- std::operator&gt;= (thread)
- std::operator&lt; (thread)
- std::operator&lt;&lt; (thread)
- std::operator&lt;= (thread)
- std::operator== (thread)
ms.openlocfilehash: 6312d14dc681736ee396d5c7af6c50ba8d72cd3a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375822"
---
# <a name="ltthreadgt-operators"></a>Операторы &lt;thread&gt;

||||
|-|-|-|
|[оператора!](#op_neq)|[Оператор&gt;](#op_gt)|[Оператор&gt;=](#op_gt_eq)|
|[Оператор&lt;](#op_lt)|[Оператор&lt;&lt;](#op_lt_lt)|[Оператор&lt;=](#op_lt_eq)|
|[оператора](#op_eq_eq)|

## <a name="operatorgt"></a><a name="op_gt_eq"></a>Оператор&gt;=

Определяет, справедливо ли, что один из объектов `thread::id` больше другого или равен ему.

```cpp
bool operator>= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Параметры

*Левой*\
Левый объект `thread::id`.

*Правильно*\
Правой объект `thread::id`.

### <a name="return-value"></a>Возвращаемое значение

`!(Left < Right)`

### <a name="remarks"></a>Remarks

Эта функция не вызывает исключений.

## <a name="operatorgt"></a><a name="op_gt"></a>Оператор&gt;

Определяет, справедливо ли, что один из объектов `thread::id` больше другого или равен ему.

```cpp
bool operator> (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Параметры

*Левой*\
Левый объект `thread::id`.

*Правильно*\
Правой объект `thread::id`.

### <a name="return-value"></a>Возвращаемое значение

`Right < Left`

### <a name="remarks"></a>Remarks

Эта функция не вызывает исключений.

## <a name="operatorlt"></a><a name="op_lt_eq"></a>Оператор&lt;=

Определяет, справедливо ли, что один из объектов `thread::id` меньше другого или равен ему.

```cpp
bool operator<= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Параметры

*Левой*\
Левый объект `thread::id`.

*Правильно*\
Правой объект `thread::id`.

### <a name="return-value"></a>Возвращаемое значение

`!(Right < Left)`

### <a name="remarks"></a>Remarks

Эта функция не вызывает исключений.

## <a name="operatorlt"></a><a name="op_lt"></a>Оператор&lt;

Определяет, справедливо ли, что один объект `thread::id` меньше другого.

```cpp
bool operator<(
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Параметры

*Левой*\
Левый объект `thread::id`.

*Правильно*\
Правой объект `thread::id`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если *левый* предшествует *право* в общем порядке; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Оператор определяет общий порядок всех объектов `thread::id`. Эти объекты могут использоваться в качестве ключей в ассоциативных контейнерах.

Эта функция не вызывает исключений.

## <a name="operator"></a><a name="op_neq"></a>оператора!

Проверяет неравенство двух объектов `thread::id`.

```cpp
bool operator!= (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Параметры

*Левой*\
Левый объект `thread::id`.

*Правильно*\
Правой объект `thread::id`.

### <a name="return-value"></a>Возвращаемое значение

`!(Left == Right)`

### <a name="remarks"></a>Remarks

Эта функция не вызывает исключений.

## <a name="operator"></a><a name="op_eq_eq"></a>оператора

Сравнивает два объекта `thread::id` на равенство.

```cpp
bool operator== (
    thread::id Left,
    thread::id Right) noexcept
```

### <a name="parameters"></a>Параметры

*Левой*\
Левый объект `thread::id`.

*Правильно*\
Правой объект `thread::id`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если эти два объекта представляют один и тот же поток выполнения или если ни один объект не представляет нить выполнения; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Эта функция не вызывает исключений.

## <a name="operatorltlt"></a><a name="op_lt_lt"></a>Оператор&lt;&lt;

Вставляет текстовое представление объекта `thread::id` в поток.

```cpp
template <class Elem, class Tr>
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& Ostr, thread::id Id);
```

### <a name="parameters"></a>Параметры

*Остр*\
Объект [basic_ostream](../standard-library/basic-ostream-class.md).

*Id*\
Объект `thread::id` .

### <a name="return-value"></a>Возвращаемое значение

*Остр*.

### <a name="remarks"></a>Remarks

Эта функция вставляет *Id* в *Ostr*.

Если два объекта `thread::id` равны, вставленные текстовые представления этих объектов совпадают.

## <a name="see-also"></a>См. также раздел

[\<нить>](../standard-library/thread.md)
