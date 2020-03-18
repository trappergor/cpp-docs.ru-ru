---
title: Операторы &lt;forward_list&gt;
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::operator!=
- forward_list/std::operator==
- forward_list/std::operatoroperator&gt;
- forward_list/std::operatoroperator&gt=;
- forward_list/std::operatoroperator&lt;
- forward_list/std::operatoroperator&lt;=
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
helpviewer_keywords:
- std::operator!= (forward_list)
- std::operator== (forward_list)
- std::operatoroperator&gt; (forward_list)
- std::operatoroperator&gt=; (forward_list)
- std::operatoroperator&lt; (forward_list)
- std::operatoroperator&lt;= (forward_list)
ms.openlocfilehash: 1ddfb56c7ff68ec10c7bb56af3495e4042acb83c
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79427089"
---
# <a name="ltforward_listgt-operators"></a>Операторы &lt;forward_list&gt;

## <a name="op_eq_eq"></a>Оператор = =

Проверяет, равен ли объект прямого списка слева от оператора объекту прямого списка справа от оператора.

```cpp
bool operator==(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `forward_list`.

*справа*\
Объект типа `forward_list`.

### <a name="remarks"></a>Remarks

Эта функция шаблона перегружает `operator==` для сравнения двух объектов шаблона класса `forward_list`. Функция возвращает `distance(left.begin(), end()) == distance(right.begin(),right.end()) && equal(left. begin(),left. end(),right.begin())`.

## <a name="op_neq"></a>operator! =

Проверяет, не равен ли объект прямого списка слева от оператора объекту прямого списка справа от оператора.

```cpp
bool operator!=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `forward_list`.

*справа*\
Объект типа `forward_list`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если списки не равны; в противном случае **false**.

### <a name="remarks"></a>Remarks

Эта функция шаблона возвращает `!(left == right)`.

## <a name="op_lt">Оператор </a>&lt;

Проверяет, меньше ли объект прямого списка слева от оператора объекта прямого списка справа от оператора.

```cpp
bool operator<(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `forward_list`.

*справа*\
Объект типа `forward_list`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если список слева от оператора меньше, чем список справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Remarks

Эта функция шаблона перегружает `operator<` для сравнения двух объектов шаблона класса `forward_list`. Функция возвращает `lexicographical_compare(lhs. begin(), lhs. end(), rhs.begin(), rhs.end())`.

## <a name="op_lt_eq"></a>&lt;оператора =

Проверяет, меньше ли (или равен) объект прямого списка слева от оператора объекта прямого списка справа от оператора.

```cpp
bool operator<=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `forward_list`.

*справа*\
Объект типа `forward_list`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если список в левой части оператора меньше или равен списку в правой части оператора; в противном случае **false**.

### <a name="remarks"></a>Remarks

Эта функция шаблона возвращает `!(right < left)`.

## <a name="op_gt">Оператор </a>&gt;

Проверяет, больше ли объект прямого списка слева от оператора объекта прямого списка справа от оператора.

```cpp
bool operator>(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `forward_list`.

*справа*\
Объект типа `forward_list`.

### <a name="return-value"></a>Возвращаемое значение

**true**, если список слева от оператора больше списка справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Remarks

Эта функция шаблона возвращает `right < left`.

## <a name="op_gt_eq"></a>&gt;оператора =

Проверяет, больше ли (или равен) объект прямого списка слева от оператора объекта прямого списка справа от оператора.

```cpp
bool operator>=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Объект типа `forward_list`.

*справа*\
Объект типа `forward_list`.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если прямой список в левой части оператора больше или равен прямому списку справа от оператора; в противном случае — **false**.

### <a name="remarks"></a>Remarks

Функция-шаблон возвращает `!(left < right)`.
