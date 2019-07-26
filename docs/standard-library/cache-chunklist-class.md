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
ms.openlocfilehash: 73730e0a4a22e7f5e63809cc2c1603cbda1ab596
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449665"
---
# <a name="cachechunklist-class"></a>Класс cache_chunklist

Задает [распределитель блоков](../standard-library/allocators-header.md), который выделяет и освобождает блоки памяти одного размера.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Sz, std::size_t Nelts = 20>
class cache_chunklist
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*SZ*|Число элементов в массиве, которые нужно выделить.|

## <a name="remarks"></a>Примечания

Этот класс шаблона использует **оператор New** для выделения блоков необработанной памяти, блоков подвыделения для выделения хранилища для блока памяти, когда это необходимо. Он хранит освобожденные блоки памяти в отдельном свободном списке для каждого фрагмента и использует **оператор DELETE** для освобождения блока, если ни один из его блоков памяти не используется.

Каждый блок памяти содержит *SZ* байты доступной памяти и указатель на блок, к которому он принадлежит. Каждый блок содержит `Nelts` блоки памяти, три указателя, int и данные, необходимые **операторам New** и **Delete** .

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[cache_chunklist](#cache_chunklist)|Создает объект типа `cache_chunklist`.|

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
|-|-|
|[allocate](#allocate)|Выделяет блок памяти.|
|[deallocate](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="allocate"></a>  cache_chunklist::allocate

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

## <a name="cache_chunklist"></a>  cache_chunklist::cache_chunklist

Создает объект типа `cache_chunklist`.

```cpp
cache_chunklist();
```

### <a name="remarks"></a>Примечания

## <a name="deallocate"></a>  cache_chunklist::deallocate

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

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)
