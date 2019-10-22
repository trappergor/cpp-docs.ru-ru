---
title: Класс cache_suballoc
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_suballoc
- allocators/stdext::cache_suballoc::allocate
- allocators/stdext::cache_suballoc::deallocate
helpviewer_keywords:
- stdext::cache_suballoc
- stdext::cache_suballoc [C++], allocate
- stdext::cache_suballoc [C++], deallocate
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
ms.openlocfilehash: 7a21f0c4f81277200ff069baf751fa013a3c0cea
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688344"
---
# <a name="cache_suballoc-class"></a>Класс cache_suballoc

Задает [распределитель блоков](../standard-library/allocators-header.md), который выделяет и освобождает блоки памяти одного размера.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Sz, size_t Nelts = 20>
class cache_suballoc
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*SZ*|Число элементов в массиве, которые нужно выделить.|

## <a name="remarks"></a>Заметки

Шаблон класса cache_suballoc сохраняет освобожденные блоки памяти в свободном списке с неограниченной длиной, используя `freelist<sizeof(Type), max_unbounded>` и подраспределяет блоки памяти из большего блока, выделенного с помощью **оператора New** , если свободный список пуст.

Каждый блок содержит `Sz * Nelts` байтов доступной памяти и данных, которые требуются **операторам New** и **Delete** . Выделенные участки памяти никогда не будут освобождены.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[cache_suballoc](#cache_suballoc)|Создает объект типа `cache_suballoc`.|

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
|-|-|
|[allocate](#allocate)|Выделяет блок памяти.|
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="allocate"></a>  cache_suballoc::allocate

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

## <a name="cache_suballoc"></a>  cache_suballoc::cache_suballoc

Создает объект типа `cache_suballoc`.

```cpp
cache_suballoc();
```

### <a name="remarks"></a>Заметки

## <a name="deallocate"></a>  cache_suballoc::deallocate

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

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)
