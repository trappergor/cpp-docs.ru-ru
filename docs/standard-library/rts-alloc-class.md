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
ms.openlocfilehash: b0ec7d4d3dbe5ef1334bf3c394819a4f5235c28c
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688979"
---
# <a name="rts_alloc-class"></a>Класс rts_alloc

Шаблон класса rts_alloc описывает [Фильтр](../standard-library/allocators-header.md) , содержащий массив экземпляров кэша, и определяет, какой экземпляр следует использовать для выделения и освобождения в среде выполнения, а не во время компиляции.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Cache>
class rts_alloc
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Кэш*|Тип экземпляров кэша, содержащихся в массиве. Возможные типы: [Класс cache_chunklist](../standard-library/cache-chunklist-class.md), [cache_freelist](../standard-library/cache-freelist-class.md) или [cache_suballoc](../standard-library/cache-suballoc-class.md).|

## <a name="remarks"></a>Заметки

Этот шаблон класса содержит несколько экземпляров распределителя блоков и определяет, какой экземпляр следует использовать для выделения или освобождения в среде выполнения, а не во время компиляции. Он используется с компиляторами, которые не могут скомпилировать повторную привязку.

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

### <a name="remarks"></a>Заметки

Функция-член возвращает `caches[_IDX].allocate(count)`, где `_IDX` индекса определяется запрошенным *количеством*размеров блоков, или, если *Count* слишком велико, он возвращает `operator new(count)`. `cache`, представляющий объект кэша.

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

### <a name="remarks"></a>Заметки

Функция-член вызывает `caches[_IDX].deallocate(ptr, count)`, где `_IDX` индекса определяется запрошенным *количеством*размеров блоков, или, если *Count* слишком велико, возвращается `operator delete(ptr)`.

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

### <a name="remarks"></a>Заметки

**значение true** , если результат `caches[0].equals(other.caches[0])`; в противном случае — **значение false**. `caches` представляет массив объектов кэша.

## <a name="see-also"></a>См. также

[ALLOCATOR_DECL](../standard-library/allocators-functions.md#allocator_decl)\
[\<allocators>](../standard-library/allocators-header.md)
