---
title: Класс cache_chunklist | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::cache_chunklist
- allocators/stdext::cache_chunklist::allocate
- allocators/stdext::cache_chunklist::deallocate
dev_langs:
- C++
helpviewer_keywords:
- stdext::cache_chunklist
- stdext::cache_chunklist [C++], allocate
- stdext::cache_chunklist [C++], deallocate
ms.assetid: af19eccc-4ae7-4a34-bbb2-81e397424cb9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 808340df89bb548fee57604f25409c117933cc4e
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953264"
---
# <a name="cachechunklist-class"></a>Класс cache_chunklist

Задает [распределитель блоков](../standard-library/allocators-header.md), который выделяет и освобождает блоки памяти одного размера.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Sz, std::size_t Nelts = 20>
class cache_chunklist
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*sz*|Число элементов в массиве, которые нужно выделить.|

## <a name="remarks"></a>Примечания

Этот класс шаблона использует **оператор new** для выделения участков неразмеченной памяти, распределяющей блоки для выделения хранилища для блока памяти при необходимости; он хранит освобожденные блоки памяти в отдельном списке свободных для каждого фрагмента данных и использует **оператор delete** для освобождения участка, когда ни один из его блоков памяти используется.

Каждый блок памяти содержит *Sz* байт свободной памяти и указатель на блок, к которому он принадлежит. Каждый блок содержит `Nelts` блоки памяти, три указателя, int и данные, **оператор new** и **оператор delete** требуют.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание:|
|-|-|
|[cache_chunklist](#cache_chunklist)|Создает объект типа `cache_chunklist`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание:|
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

|Параметр|Описание:|
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

|Параметр|Описание:|
|---------------|-----------------|
|*ptr*|Указатель на первый объект, который необходимо освободить из хранилища.|
|*count*|Количество объектов для освобождения из хранилища.|

### <a name="remarks"></a>Примечания

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)<br/>
