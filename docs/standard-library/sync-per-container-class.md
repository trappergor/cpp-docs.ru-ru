---
title: Класс sync_per_container
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
helpviewer_keywords:
- sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
ms.openlocfilehash: 378451ac2643d62271fd9e7fa44706a84ee8bb83
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450292"
---
# <a name="syncpercontainer-class"></a>Класс sync_per_container

Описывает [фильтр синхронизации](../standard-library/allocators-header.md), предоставляющий отдельный объект кэша для каждого объекта распределителя.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Cache>
class sync_per_container
    : public Cache
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Кэш*|Тип кэша, связанный с фильтром синхронизации. Возможные типы: [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) или [cache_suballoc](../standard-library/cache-suballoc-class.md).|

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
|-|-|
|[equals](#equals)|Сравнивает два кэша на равенство.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="equals"></a>  sync_per_container::equals

Сравнивает два кэша на равенство.

```cpp
bool equals(const sync_per_container<Cache>& Other) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Кэш*|Объект кэша фильтра синхронизации.|
|*Другое*|Объект кэша для сравнения на равенство.|

### <a name="return-value"></a>Возвращаемое значение

Функция члена всегда возвращает **значение false**.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)
