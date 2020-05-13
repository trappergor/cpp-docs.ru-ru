---
title: Класс sync_shared
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::sync_shared
- allocators/stdext::sync_shared::allocate
- allocators/stdext::sync_shared::deallocate
- allocators/stdext::sync_shared::equals
helpviewer_keywords:
- stdext::sync_shared
- stdext::sync_shared [C++], allocate
- stdext::sync_shared [C++], deallocate
- stdext::sync_shared [C++], equals
ms.assetid: cab3af9e-3d1a-4f2c-8580-0f89e5687d8e
ms.openlocfilehash: 029edea59f29534491232d5d99353ccb093447bd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376524"
---
# <a name="sync_shared-class"></a>Класс sync_shared

Описывает [фильтр синхронизации,](../standard-library/allocators-header.md) который использует mutex для управления доступом к объекту кэша, который является общим для всех разглашений.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Cache>
class sync_shared
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Кэш*|Тип кэша, связанный с фильтром синхронизации. Возможные типы: [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) или [cache_suballoc](../standard-library/cache-suballoc-class.md).|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Выделить](#allocate)|Выделяет блок памяти.|
|[Освобождения](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|
|[equals](#equals)|Сравнивает два кэша на равенство.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="sync_sharedallocate"></a><a name="allocate"></a>sync_shared::

Выделяет блок памяти.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*count*|Число выделяемых элементов в массиве.|

### <a name="return-value"></a>Возвращаемое значение

Указатель на выделяемый объект.

### <a name="remarks"></a>Remarks

Функция-член блокирует мьютекс, вызывает метод `cache.allocate(count)`, разблокирует мьютекс и возвращает результат более раннего вызова `cache.allocate(count)`. `cache` представляет текущий объект кэша.

## <a name="sync_shareddeallocate"></a><a name="deallocate"></a>sync_shared::d

Освобождает указанное число объектов из памяти, начиная с заданной позиции.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Ptr*|Указатель на первый объект, который должен быть освобожден из хранилища.|
|*count*|Количество объектов для освобождения из хранилища.|

### <a name="remarks"></a>Remarks

Эта функция-член блокирует мьютекс, вызывает метод `cache.deallocate(ptr, count)`, где `cache` представляет объект кэша, а затем разблокирует мьютекс.

## <a name="sync_sharedequals"></a><a name="equals"></a>sync_shared::равные

Сравнивает два кэша на равенство.

```cpp
bool equals(const sync_shared<Cache>& Other) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Кэш*|Тип кэша, связанный с фильтром синхронизации.|
|*Прочее*|Кэш для сравнения на равенство.|

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `cache.equals(Other.cache)`результат `cache` , где представляет объект кэша, **это правда;** в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>См. также раздел

[\<>-подлатыватели](../standard-library/allocators-header.md)
