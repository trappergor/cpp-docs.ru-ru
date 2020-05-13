---
title: Класс rts_alloc
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::rts_alloc
- allocators/stdext::rts_alloc::allocate
- allocators/stdext::rts_alloc::deallocate
- allocators/stdext::rts_alloc::equals
helpviewer_keywords:
- stdext::rts_alloc
- stdext::rts_alloc [C++], allocate
- stdext::rts_alloc [C++], deallocate
- stdext::rts_alloc [C++], equals
ms.assetid: ab41bffa-83d1-4a1c-87b9-5707d516931f
ms.openlocfilehash: 6ed84d906944a09fa355e281640e9480f3173554
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373425"
---
# <a name="rts_alloc-class"></a>Класс rts_alloc

Шаблон rts_alloc класса описывает [фильтр,](../standard-library/allocators-header.md) который содержит массив экземпляров кэша, и определяет, какой экземпляр использовать для распределения и распределения во время выполнения, а не во время компиляции.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Cache>
class rts_alloc
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Кэш*|Тип экземпляров кэша, содержащихся в массиве. Возможные типы: [Класс cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) или [cache_suballoc](../standard-library/cache-suballoc-class.md).|

## <a name="remarks"></a>Remarks

Этот шаблон класса содержит несколько экземпляров разлляции блоков и определяет, какой экземпляр использовать для распределения или размещения сделки во время выполнения, а не во время компиляции. Он используется с компиляторами, которые не могут скомпилировать повторную привязку.

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Выделить](#allocate)|Выделяет блок памяти.|
|[Освобождения](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|
|[equals](#equals)|Сравнивает два кэша на равенство.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="rts_allocallocate"></a><a name="allocate"></a>rts_alloc::

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

Функция участника `caches[_IDX].allocate(count)`возвращается, `_IDX` когда индекс определяется количеством *запрашиваемого*размера блока, или, `operator new(count)`если *счет* слишком велик, он возвращается. `cache`, представляющий объект кэша.

## <a name="rts_allocdeallocate"></a><a name="deallocate"></a>rts_alloc::d

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

Функция участника `caches[_IDX].deallocate(ptr, count)`вызывает, когда `_IDX` индекс определяется количеством *запрашиваемого*размера блока, или, `operator delete(ptr)`если *счет* слишком велик, он возвращается.

## <a name="rts_allocequals"></a><a name="equals"></a>rts_alloc::равные

Сравнивает два кэша на равенство.

```cpp
bool equals(const sync<_Cache>& _Other) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*_Cache*|Объект кэша, связанный с фильтром.|
|*_Other*|Объект кэша для сравнения на равенство.|

### <a name="remarks"></a>Remarks

**верно,** если `caches[0].equals(other.caches[0])`результат ; в противном случае, **ложные**. `caches` представляет массив объектов кэша.

## <a name="see-also"></a>См. также раздел

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)\
[\<>-подлатыватели](../standard-library/allocators-header.md)
