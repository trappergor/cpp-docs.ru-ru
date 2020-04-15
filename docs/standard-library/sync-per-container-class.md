---
title: Класс sync_per_container
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_per_container
- allocators/stdext::sync_per_container::equals
helpviewer_keywords:
- sync_per_container class
ms.assetid: 0b4b2904-b668-4d94-a422-d4f919cbffab
ms.openlocfilehash: 2c60911b5469cbf74944c9f63af44f2351790280
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376553"
---
# <a name="sync_per_container-class"></a>Класс sync_per_container

Описывает [фильтр синхронизации,](../standard-library/allocators-header.md) который предоставляет отдельный объект кэша для каждого объекта выделения.

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

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[equals](#equals)|Сравнивает два кэша на равенство.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="sync_per_containerequals"></a><a name="equals"></a>sync_per_container::равные

Сравнивает два кэша на равенство.

```cpp
bool equals(const sync_per_container<Cache>& Other) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Кэш*|Объект кэша фильтра синхронизации.|
|*Прочее*|Объект кэша для сравнения на равенство.|

### <a name="return-value"></a>Возвращаемое значение

Функция участника всегда возвращает **ложное**.

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>См. также раздел

[\<>-подлатыватели](../standard-library/allocators-header.md)
