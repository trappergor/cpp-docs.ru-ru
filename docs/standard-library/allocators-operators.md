---
title: Операторы &lt;allocators&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
dev_langs:
- C++
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: 25e40157c1872df3e970bb234accab5c487c6287
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="ltallocatorsgt-operators"></a>Операторы &lt;allocator&gt;

Имеются функции оператор общий шаблон, определенный в &lt;распределителей&gt;. Для функций операторов членов класса см. в документации по классу.

|||
|-|-|
|[оператор!=](#op_neq)|[оператор==](#op_eq_eq)|

## <a name="op_neq"></a> operator!=

Проверяет на неравенство между объектами распределителя указанного класса.

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`left`|Один из объектов allocator для проверки на неравенство.|
|`right`|Один из объектов allocator для проверки на неравенство.|

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если объекты allocator не равны; значение **false**, если объекты allocator равны.

### <a name="remarks"></a>Примечания

Оператор шаблона возвращает `!(left == right)`.

## <a name="op_eq_eq"></a>  operator==

Проверяет на равенство объекты распределителя указанного класса.

```cpp
template <class Type, class Sync>
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`left`|Один из объектов allocator для проверки на равенство.|
|`right`|Один из объектов allocator для проверки на равенство.|

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если объекты allocator равны; значение **false**, если объекты allocator не равны.

### <a name="remarks"></a>Примечания

Этот оператор шаблона возвращает `left.equals(right)`.

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)
