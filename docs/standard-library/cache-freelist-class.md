---
title: Класс cache_freelist | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::cache_freelist
- allocators/stdext::cache_freelist::allocate
- allocators/stdext::cache_freelist::deallocate
dev_langs:
- C++
helpviewer_keywords:
- stdext::cache_freelist
- stdext::cache_freelist [C++], allocate
- stdext::cache_freelist [C++], deallocate
ms.assetid: 840694de-36ba-470f-8dae-2b723d5a8cd9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8478490914a6f9049cd54ec78c8de8a1e519f36f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="cachefreelist-class"></a>Класс cache_freelist

Задает [распределитель блоков](../standard-library/allocators-header.md), который выделяет и освобождает блоки памяти одного размера.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Sz, class Max>
class cache_freelist
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`Sz`|Число элементов в массиве, которые нужно выделить.|
|`Max`|Класс max, представляющий максимальный размер списка свободных блоков. Это может быть класс [max_fixed_size](../standard-library/max-fixed-size-class.md), [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md) или [max_variable_size](../standard-library/max-variable-size-class.md).|

## <a name="remarks"></a>Примечания

Класс шаблона cache_freelist ведет список свободных блоков памяти размером `Sz`. При заполнении списка свободных блоков он использует `operator delete` для освобождения блоков памяти. Когда список свободных блоков пустой, он использует `operator new` для выделения новых блоков памяти. Максимальный размер списка свободных блоков определяется классом max, переданным в параметре `Max`.

Каждый блок памяти содержит `Sz` байт свободной памяти и данных, которые требуются `operator new` и `operator delete`.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[cache_freelist](#cache_freelist)|Создает объект типа `cache_freelist`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[allocate](#allocate)|Выделяет блок памяти.|
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="allocate"></a>  cache_freelist::allocate

Выделяет блок памяти.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`count`|Число элементов в массиве, которые нужно выделить.|

### <a name="return-value"></a>Возвращаемое значение

Указатель на выделяемый объект.

### <a name="remarks"></a>Примечания

## <a name="cache_freelist"></a>  cache_freelist::cache_freelist

Создает объект типа `cache_freelist`.

```cpp
cache_freelist();
```

### <a name="remarks"></a>Примечания

## <a name="deallocate"></a>  cache_freelist::deallocate

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

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)<br/>
