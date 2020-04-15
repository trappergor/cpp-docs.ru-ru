---
title: Класс cache_chunklist
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
helpviewer_keywords:
- stdext::cache_chunklist
- stdext::cache_chunklist [C++], allocate
- stdext::cache_chunklist [C++], deallocate
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
ms.openlocfilehash: d0dd6176a34bd625069511106c491225d1467d08
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366754"
---
# <a name="cache_chunklist-class"></a>Класс cache_chunklist

Задает [распределитель блоков](../standard-library/allocators-header.md), который выделяет и освобождает блоки памяти одного размера.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Sz, std::size_t Nelts = 20>
class cache_chunklist
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Sz*|Число выделяемых элементов в массиве.|

## <a name="remarks"></a>Remarks

Этот шаблон класса использует **новый оператор** для выделения фрагментов сырой памяти, подделывая блоки для выделения хранилища для блока памяти, когда это необходимо; он хранит блоки памяти в отдельном свободном списке для каждого куска, и использует **удаление оператора** для того чтобы deallocate ломку когда никакие из своих блоков памяти в пользе.

Каждый блок памяти содержит *Sz* байты применяемой в уотек памяти и указатель на кусок, который он принадлежит. Каждый `Nelts` кусок содержит блоки памяти, три указателя, Int и данные, которые **оператор новый** и **оператор удалить** требуют.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[cache_chunklist](#cache_chunklist)|Создает объект типа `cache_chunklist`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Выделить](#allocate)|Выделяет блок памяти.|
|[Освобождения](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="cache_chunklistallocate"></a><a name="allocate"></a>cache_chunklist::

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

## <a name="cache_chunklistcache_chunklist"></a><a name="cache_chunklist"></a>cache_chunklist::cache_chunklist

Создает объект типа `cache_chunklist`.

```cpp
cache_chunklist();
```

### <a name="remarks"></a>Remarks

## <a name="cache_chunklistdeallocate"></a><a name="deallocate"></a>cache_chunklist::dраспределение

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

## <a name="see-also"></a>См. также раздел

[\<>-подлатыватели](../standard-library/allocators-header.md)
