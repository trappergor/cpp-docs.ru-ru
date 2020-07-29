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
ms.openlocfilehash: 9f1a984d38bed9dd3795164e355c7ccac100ae6b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232889"
---
# <a name="sync_shared-class"></a>Класс sync_shared

Описывает [фильтр синхронизации](../standard-library/allocators-header.md) , использующий мьютекс для управления доступом к объекту кэша, который совместно используется всеми распределителями.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Cache>
class sync_shared
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*Кэш*|Тип кэша, связанный с фильтром синхронизации. Возможные типы: [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) или [cache_suballoc](../standard-library/cache-suballoc-class.md).|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[allocate](#allocate)|Выделяет блок памяти.|
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|
|[equals](#equals)|Сравнивает два кэша на равенство.|

## <a name="requirements"></a>Требования

**Заголовок:**\<allocators>

**Пространство имен:** stdext

## <a name="sync_sharedallocate"></a><a name="allocate"></a>sync_shared:: allocate

Выделяет блок памяти.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*count*|Число выделяемых элементов в массиве.|

### <a name="return-value"></a>Возвращаемое значение

Указатель на выделяемый объект.

### <a name="remarks"></a>Remarks

Функция-член блокирует мьютекс, вызывает метод `cache.allocate(count)`, разблокирует мьютекс и возвращает результат более раннего вызова `cache.allocate(count)`. `cache` представляет текущий объект кэша.

## <a name="sync_shareddeallocate"></a><a name="deallocate"></a>sync_shared::d еаллокате

Освобождает указанное число объектов из памяти, начиная с заданной позиции.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*ptr*|Указатель на первый объект, который должен быть освобожден из хранилища.|
|*count*|Количество объектов для освобождения из хранилища.|

### <a name="remarks"></a>Remarks

Эта функция-член блокирует мьютекс, вызывает метод `cache.deallocate(ptr, count)`, где `cache` представляет объект кэша, а затем разблокирует мьютекс.

## <a name="sync_sharedequals"></a><a name="equals"></a>sync_shared:: Equals

Сравнивает два кэша на равенство.

```cpp
bool equals(const sync_shared<Cache>& Other) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*Кэш*|Тип кэша, связанный с фильтром синхронизации.|
|*Другое*|Кэш для сравнения на равенство.|

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если результат `cache.equals(Other.cache)` , где `cache` представляет объект кэша, равен **`true`** ; в противном случае — **`false`** .

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>См. также раздел

[\<allocators>](../standard-library/allocators-header.md)
