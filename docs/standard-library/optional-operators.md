---
title: '&lt;дополнительные&gt; операторы'
ms.date: 11/04/2016
f1_keywords:
- optional/std::operator!=
- optional/std::operator==
- optional/std::operatoroperator&gt;
- optional/std::operatoroperator&gt=;
- optional/std::operatoroperator&lt;
- optional/std::operatoroperator&lt;=
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
helpviewer_keywords:
- std::operator!= (optional)
- std::operator== (optional)
- std::operatoroperator&gt; (optional)
- std::operatoroperator&gt=; (optional)
- std::operatoroperator&lt; (optional)
- std::operatoroperator&lt;= (optional)
ms.openlocfilehash: 9bdef0669f90da7865f7652ff4528e51e584e1a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373633"
---
# <a name="ltoptionalgt-operators"></a>&lt;дополнительные&gt; операторы

## <a name="operator"></a><a name="op_eq_eq"></a>оператора

Проверяет равенство объекта `optional` слева от оператора объекту `optional` справа от оператора.

```cpp
template <class T, class U> constexpr bool operator==(const optional<T>& left, const optional<U>& right);
template <class T> constexpr bool operator==(const optional<T>& left, nullopt_t right) noexcept;
template <class T> constexpr bool operator==(nullopt_t left, const optional<T>& right) noexcept;
template <class T, class U> constexpr bool operator==(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator==(const U&, const optional<T>&);
```

### <a name="parameters"></a>Параметры

*Левой*\
Объект типа, `optional` `nullopt_t`или `T`.

*Правильно*\
Объект типа, `optional` `nullopt_t`или `T`.

## <a name="operator"></a><a name="op_neq"></a>оператора!

Проверяет неравенство объекта `optional` слева от оператора объекту `optional` справа от оператора.

```cpp
template <class T, class U> constexpr bool operator!=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator!=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator!=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator!=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator!=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Параметры

*Левой*\
Объект типа, `optional` `nullopt_t`или `T`.

*Правильно*\
Объект типа, `optional` `nullopt_t`или `T`.

### <a name="remarks"></a>Remarks

Эта функция шаблона возвращает `!(left == right)`.

## <a name="operatorlt"></a><a name="op_lt"></a>Оператор&lt;

Проверяет, меньше ли объект `optional` слева от оператора, чем объект `optional` справа от оператора.

```cpp
template <class T, class U> constexpr bool operator<(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<(const U&, const optional<T>&);
```

### <a name="parameters"></a>Параметры

*Левой*\
Объект типа, `optional` `nullopt_t`или `T`.

*Правильно*\
Объект типа, `optional` `nullopt_t`или `T`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если список слева от оператора меньше, чем список справа от оператора; в противном случае **false**.

## <a name="operatorlt"></a><a name="op_lt_eq"></a>Оператор&lt;=

Проверяет, меньше ли объект `optional` слева от оператора, чем объект `optional` справа от оператора, или равен ему.

```cpp
template <class T, class U> constexpr bool operator<=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator<=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator<=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator<=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator<=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Параметры

*Левой*\
Объект типа, `optional` `nullopt_t`или `T`.

*Правильно*\
Объект типа, `optional` `nullopt_t`или `T`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если список в левой части оператора меньше или равен списку в правой части оператора; в противном случае **false**.

### <a name="remarks"></a>Remarks

Эта функция шаблона возвращает `!(right < left)`.

## <a name="operatorgt"></a><a name="op_gt"></a>Оператор&gt;

Проверяет больше ли объект `optional` слева от оператора, чем объект `optional` справа от оператора.

```cpp
template <class T, class U> constexpr bool operator>(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>(const U&, const optional<T>&);
```

### <a name="parameters"></a>Параметры

*Левой*\
Объект типа, `optional` `nullopt_t`или `T`.

*Правильно*\
Объект типа, `optional` `nullopt_t`или `T`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если список слева от оператора больше списка справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Remarks

Эта функция шаблона возвращает `right < left`.

## <a name="operatorgt"></a><a name="op_gt_eq"></a>Оператор&gt;=

Проверяет больше ли объект `optional` слева от оператора, чем объект `optional` справа от оператора, или равен ему.

```cpp
template <class T, class U> constexpr bool operator>=(const optional<T>&, const optional<U>&);
template <class T> constexpr bool operator>=(const optional<T>&, nullopt_t) noexcept;
template <class T> constexpr bool operator>=(nullopt_t, const optional<T>&) noexcept;
template <class T, class U> constexpr bool operator>=(const optional<T>&, const U&);
template <class T, class U> constexpr bool operator>=(const U&, const optional<T>&);
```

### <a name="parameters"></a>Параметры

*Левой*\
Объект типа, `optional` `nullopt_t`или `T`.

*Правильно*\
Объект типа, `optional` `nullopt_t`или `T`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если `optional` слева от оператора больше или равен `optional` справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Remarks

Функция шаблона возвращает `!(left < right)`.
