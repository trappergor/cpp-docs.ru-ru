---
title: "Операторы &lt;allocators&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
dev_langs:
- C++
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: e84f3c66adaf4d4d0cd5af68ee51841025bd89b2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ltallocatorsgt-operators"></a>Операторы &lt;allocator&gt;

Имеются функции оператор общий шаблон, определенный в &lt;распределителей&gt;. Для функций операторов членов класса см. в документации по классу.

|||
|-|-|
|[оператор!=](#op_neq)|[оператор==](#op_eq_eq)|

##  <a name="op_neq"></a> operator!=

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
|`left`|Один из объектов allocator для проверки на неравенство.|
|`right`|Один из объектов allocator для проверки на неравенство.|

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если объекты allocator не равны; значение **false**, если объекты allocator равны.

### <a name="remarks"></a>Примечания

Оператор шаблона возвращает `!(left == right)`.

##  <a name="op_eq_eq"></a>  operator==

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
|`left`|Один из объектов allocator для проверки на равенство.|
|`right`|Один из объектов allocator для проверки на равенство.|

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если объекты allocator равны; значение **false**, если объекты allocator не равны.

### <a name="remarks"></a>Примечания

Этот оператор шаблона возвращает `left.equals(right)`.

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)  
