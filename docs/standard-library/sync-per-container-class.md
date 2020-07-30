---
title: Класс sync_per_container
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
helpviewer_keywords:
- sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
ms.openlocfilehash: d38307c4ae19e5f87d0dbcca8943dc1c3f239917
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232902"
---
# <a name="sync_per_container-class"></a>Класс sync_per_container

Описывает [фильтр синхронизации](../standard-library/allocators-header.md) , который предоставляет отдельный объект кэша для каждого объекта распределителя.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Cache>
class sync_per_container
    : public Cache
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*Кэш*|Тип кэша, связанный с фильтром синхронизации. Возможные типы: [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) или [cache_suballoc](../standard-library/cache-suballoc-class.md).|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[equals](#equals)|Сравнивает два кэша на равенство.|

## <a name="requirements"></a>Требования

**Заголовок:**\<allocators>

**Пространство имен:** stdext

## <a name="sync_per_containerequals"></a><a name="equals"></a>sync_per_container:: Equals

Сравнивает два кэша на равенство.

```cpp
bool equals(const sync_per_container<Cache>& Other) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*Кэш*|Объект кэша фильтра синхронизации.|
|*Другое*|Объект кэша для сравнения на равенство.|

### <a name="return-value"></a>Возвращаемое значение

Функция – член всегда возвращает значение **`false`** .

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>См. также раздел

[\<allocators>](../standard-library/allocators-header.md)
