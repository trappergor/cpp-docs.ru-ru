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
ms.openlocfilehash: 065c0eaf936a438f48dbb8aa28704e0f53926a03
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451138"
---
# <a name="rtsalloc-class"></a>Класс rts_alloc

Класс шаблона rts_alloc описывает [фильтр](../standard-library/allocators-header.md), содержащий массив экземпляров кэша, и определяет, какой экземпляр нужно использовать для выделения и освобождения во время выполнения, а не во время компиляции.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Cache>
class rts_alloc
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Кэш*|Тип экземпляров кэша, содержащихся в массиве. Возможные типы: [Класс cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) или [cache_suballoc](../standard-library/cache-suballoc-class.md).|

## <a name="remarks"></a>Примечания

Этот класс шаблона содержит несколько экземпляров распределителей блоков и определяет, какой экземпляр нужно использовать для выделения и освобождения во время выполнения, а не во время компиляции. Он используется с компиляторами, которые не могут скомпилировать повторную привязку.

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
|-|-|
|[allocate](#allocate)|Выделяет блок памяти.|
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|
|[equals](#equals)|Сравнивает два кэша на равенство.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="allocate"></a>  rts_alloc::allocate

Выделяет блок памяти.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*count*|Число элементов в массиве, которые нужно выделить.|

### <a name="return-value"></a>Возвращаемое значение

Указатель на выделяемый объект.

### <a name="remarks"></a>Примечания

Функция-член возвращает `caches[_IDX].allocate(count)`, где индекс `_IDX` определяется запрошенным количеством размеров блоков, или, если *Count* слишком велик, возвращается значение `operator new(count)`. `cache`, представляющий объект кэша.

## <a name="deallocate"></a>  rts_alloc::deallocate

Освобождает указанное число объектов из памяти, начиная с заданной позиции.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*ptr*|Указатель на первый объект, который необходимо освободить из хранилища.|
|*count*|Количество объектов для освобождения из хранилища.|

### <a name="remarks"></a>Примечания

Функция-член вызывает `caches[_IDX].deallocate(ptr, count)`, где индекс `_IDX` определяется запрошенным количеством размеров блока, или, если *Count* слишком велик, возвращается значение `operator delete(ptr)`.

## <a name="equals"></a>  rts_alloc::equals

Сравнивает два кэша на равенство.

```cpp
bool equals(const sync<_Cache>& _Other) const;
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*_Cache*|Объект кэша, связанный с фильтром.|
|*_Other*|Объект кэша для сравнения на равенство.|

### <a name="remarks"></a>Примечания

**значение true** , если результат `caches[0].equals(other.caches[0])`; в противном случае — **значение false**. `caches` представляет массив объектов кэша.

## <a name="see-also"></a>См. также

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)\
[\<allocators>](../standard-library/allocators-header.md)
