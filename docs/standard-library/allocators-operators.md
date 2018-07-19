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
ms.openlocfilehash: 0bc4ce7c36d3ba097b04b1704fea7633eb7d26ea
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962960"
---
# <a name="ltallocatorsgt-operators"></a>Операторы &lt;allocator&gt;

Ниже приведены функции оператор глобального шаблона, определенные в &lt;Распределители&gt;. Оператор функции-члены класса см. в документации по классу.

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

|Параметр|Описание:|
|---------------|-----------------|
|*left*|Один из объектов allocator для проверки на неравенство.|
|*right*|Один из объектов allocator для проверки на неравенство.|

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

|Параметр|Описание:|
|---------------|-----------------|
|*left*|Один из объектов allocator для проверки на равенство.|
|*right*|Один из объектов allocator для проверки на равенство.|

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если объекты allocator равны; значение **false**, если объекты allocator не равны.

### <a name="remarks"></a>Примечания

Этот оператор шаблона возвращает `left.equals(right)`.

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)
