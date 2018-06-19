---
title: Класс sync_per_thread | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::sync_per_thread
- allocators/stdext::sync_per_thread::allocate
- allocators/stdext::sync_per_thread::deallocate
- allocators/stdext::sync_per_thread::equals
dev_langs:
- C++
helpviewer_keywords:
- stdext::sync_per_thread
- stdext::sync_per_thread [C++], allocate
- stdext::sync_per_thread [C++], deallocate
- stdext::sync_per_thread [C++], equals
ms.assetid: 47bf75f8-5b02-4760-b1d3-3099d08fe14c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e366f9b0cf92aed9c61609642f48f0e5cc9530d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858774"
---
# <a name="syncperthread-class"></a>Класс sync_per_thread

Описывает [фильтр синхронизации](../standard-library/allocators-header.md), предоставляющий отдельный объект кэширования для каждого потока.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Cache>
class sync_per_thread
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`Cache`|Тип кэша, связанный с фильтром синхронизации. Возможные типы: [cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) или [cache_suballoc](../standard-library/cache-suballoc-class.md).|

## <a name="remarks"></a>Примечания

Распределители, использующие `sync_per_thread`, могут быть равны несмотря на то, что блоки, выделенные в одном потоке, невозможно освободить из другого потока. При использовании одного из этих распределителей блоки памяти, выделенные в одном потоке, не должны быть видимы другим потокам. На практике это означает, что доступ к контейнеру, использующему один из этих распределителей, должен осуществляться только одним потоком.

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[allocate](#allocate)|Выделяет блок памяти.|
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|
|[equals](#equals)|Сравнивает два кэша на равенство.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="allocate"></a>  sync_per_thread::allocate

Выделяет блок памяти.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`count`|Число элементов в массиве, которые нужно выделить.|

### <a name="remarks"></a>Примечания

Функция-член возвращает результат вызова `cache::allocate(count)` в объекте кэша, который относится к текущему потоку. Если объект кэша для текущего потока не выделен, сначала такой объект будет выделен.

## <a name="deallocate"></a>  sync_per_thread::deallocate

Освобождает указанное число объектов из памяти, начиная с заданной позиции.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`ptr`|Указатель на первый объект, который необходимо освободить из хранилища.|
|`count`|Количество объектов для освобождения из хранилища.|

### <a name="remarks"></a>Примечания

Функция-член вызывает метод `deallocate` в объекте кэша, который относится к текущему потоку. Если объект кэша для текущего потока не выделен, сначала такой объект будет выделен.

## <a name="equals"></a>  sync_per_thread::equals

Сравнивает два кэша на равенство.

```cpp
bool equals(const sync<Cache>& Other) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`Cache`|Объект кэша фильтра синхронизации.|
|`Other`|Объект кэша для сравнения на равенство.|

### <a name="return-value"></a>Возвращаемое значение

Значение `false`, если объект кэша не выделен для этого объекта или для `Other` в текущем потоке. В противном случае возвращается результат применения `operator==` к двум объектам кэша.

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)<br/>
