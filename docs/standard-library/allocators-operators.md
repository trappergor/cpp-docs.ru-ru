---
title: Операторы &lt;allocator&gt;
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: b7429e298cdf14d727fc481db6c4a3bf8574b5e7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62377901"
---
# <a name="ltallocatorsgt-operators"></a>Операторы &lt;allocator&gt;

Ниже приведены функции оператор глобального шаблона, определенные в &lt;Распределители&gt;. Оператор функции-члены класса см. в документации по классу.

|||
|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|

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

|Параметр|Описание|
|---------------|-----------------|
|*left*|Один из объектов allocator для проверки на равенство.|
|*right*|Один из объектов allocator для проверки на равенство.|

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если объекты allocator равны; значение **false**, если объекты allocator не равны.

### <a name="remarks"></a>Примечания

Этот оператор шаблона возвращает `left.equals(right)`.

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)
