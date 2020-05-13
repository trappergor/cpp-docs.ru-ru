---
title: Операторы &lt;allocator&gt;
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: 7bc37e98ed85582cac8fc7ae21e54a6d5da9e06f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364963"
---
# <a name="ltallocatorsgt-operators"></a>Операторы &lt;allocator&gt;

Это функции глобального шаблонного оператора, определяемые в &lt;раздателях.&gt; Для функций оператора-члена класса см.

|||
|-|-|
|[оператора!](#op_neq)|[оператора](#op_eq_eq)|

## <a name="operator"></a><a name="op_neq"></a>оператора!

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
|*Левой*|Один из объектов allocator для проверки на неравенство.|
|*Правильно*|Один из объектов allocator для проверки на неравенство.|

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если объекты allocator не равны; значение **false**, если объекты allocator равны.

### <a name="remarks"></a>Remarks

Оператор-шаблон возвращает `!(left == right)`.

## <a name="operator"></a><a name="op_eq_eq"></a>оператора

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
|*Левой*|Один из объектов allocator для проверки на равенство.|
|*Правильно*|Один из объектов allocator для проверки на равенство.|

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если объекты allocator равны; значение **false**, если объекты allocator не равны.

### <a name="remarks"></a>Remarks

Этот оператор шаблона возвращает `left.equals(right)`.

## <a name="see-also"></a>См. также раздел

[\<>-подлатыватели](../standard-library/allocators-header.md)
