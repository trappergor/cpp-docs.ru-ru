---
title: Операторы &lt;forward_list&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- forward_list/std::operator!=
- forward_list/std::operator==
- forward_list/std::operatoroperator&gt;
- forward_list/std::operatoroperator&gt=;
- forward_list/std::operatoroperator&lt;
- forward_list/std::operatoroperator&lt;=
dev_langs:
- C++
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
caps.latest.revision: 11
manager: ghogen
helpviewer_keywords:
- std::operator!= (forward_list)
- std::operator== (forward_list)
- std::operatoroperator&gt; (forward_list)
- std::operatoroperator&gt=; (forward_list)
- std::operatoroperator&lt; (forward_list)
- std::operatoroperator&lt;= (forward_list)
ms.openlocfilehash: 2e0955b6f2063c8a5dbfa3f27c4e5ca18763d129
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="ltforwardlistgt-operators"></a>Операторы &lt;forward_list&gt;

||||
|-|-|-|
|[оператор!=](#op_neq)|[оператор&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[оператор&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[оператор==](#op_eq_eq)|

## <a name="op_eq_eq"></a> operator==

Проверяет, равен ли объект прямого списка слева от оператора объекту прямого списка справа от оператора.

```cpp
bool operator==(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`left`|Объект типа `forward_list`.|
|`right`|Объект типа `forward_list`.|

### <a name="remarks"></a>Примечания

Эта функция шаблона перегружает `operator==` для сравнения двух объектов класса шаблона `forward_list`. Функция возвращает `distance(left.begin(), end()) == distance(right.begin(),right.end()) && equal(left. begin(),left. end(),right.begin())`.

## <a name="op_neq"></a> operator!=

Проверяет, не равен ли объект прямого списка слева от оператора объекту прямого списка справа от оператора.

```cpp
bool operator!=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`left`|Объект типа `forward_list`.|
|`right`|Объект типа `forward_list`.|

### <a name="return-value"></a>Возвращаемое значение

**true**, если списки не равны; в противном случае **false**.

### <a name="remarks"></a>Примечания

Эта функция шаблона возвращает `!(left == right)`.

## <a name="op_lt"></a> operator&lt;

Проверяет, меньше ли объект прямого списка слева от оператора объекта прямого списка справа от оператора.

```cpp
bool operator<(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`left`|Объект типа `forward_list`.|
|`right`|Объект типа `forward_list`.|

### <a name="return-value"></a>Возвращаемое значение

`true`, если список слева от оператора меньше (но не равен) списка справа от оператора; в противном случае `false`.

### <a name="remarks"></a>Примечания

Эта функция шаблона перегружает `operator<` для сравнения двух объектов класса шаблона `forward_list`. Функция возвращает `lexicographical_compare(lhs. begin(), lhs. end(), rhs.begin(), rhs.end())`.

## <a name="op_lt_eq"></a> operator&lt;=

Проверяет, меньше ли (или равен) объект прямого списка слева от оператора объекта прямого списка справа от оператора.

```cpp
bool operator<=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`left`|Объект типа `forward_list`.|
|`right`|Объект типа `forward_list`.|

### <a name="return-value"></a>Возвращаемое значение

`true`, если список слева от оператора меньше или равен списку справа от оператора; в противном случае `false`.

### <a name="remarks"></a>Примечания

Эта функция шаблона возвращает `!(right < left)`.

## <a name="op_gt"></a> operator&gt;

Проверяет, больше ли объект прямого списка слева от оператора объекта прямого списка справа от оператора.

```cpp
bool operator>(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`left`|Объект типа `forward_list`.|
|`right`|Объект типа `forward_list`.|

### <a name="return-value"></a>Возвращаемое значение

`true`, если список слева от оператора больше списка справа от оператора; в противном случае `false`.

### <a name="remarks"></a>Примечания

Эта функция шаблона возвращает `right < left`.

## <a name="op_gt_eq"></a> operator&gt;=

Проверяет, больше ли (или равен) объект прямого списка слева от оператора объекта прямого списка справа от оператора.

```cpp
bool operator>=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`left`|Объект типа `forward_list`.|
|`right`|Объект типа `forward_list`.|

### <a name="return-value"></a>Возвращаемое значение

`true`, если список слева от оператора больше или равен списку справа от оператора; в противном случае `false`.

### <a name="remarks"></a>Примечания

Эта функция шаблона возвращает `!(left < right)`.

## <a name="see-also"></a>См. также

[<forward_list>](../standard-library/forward-list.md)<br/>
