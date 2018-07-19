---
title: Класс max_variable_size | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::max_variable_size
- allocators/stdext::max_variable_size::allocated
- allocators/stdext::max_variable_size::deallocated
- allocators/stdext::max_variable_size::full
- allocators/stdext::max_variable_size::released
- allocators/stdext::max_variable_size::saved
dev_langs:
- C++
helpviewer_keywords:
- stdext::max_variable_size
- stdext::max_variable_size [C++], allocated
- stdext::max_variable_size [C++], deallocated
- stdext::max_variable_size [C++], full
- stdext::max_variable_size [C++], released
- stdext::max_variable_size [C++], saved
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 974cee757708b9f7b1e48ea3bec3c4af98ced558
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957660"
---
# <a name="maxvariablesize-class"></a>Класс max_variable_size

Описывает объект [max class](../standard-library/allocators-header.md), который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) до значения, приблизительно пропорционального количеству выделенных блоков памяти.

## <a name="syntax"></a>Синтаксис

```cpp
class max_variable_size
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание:|
|-|-|
|[max_variable_size](#max_variable_size)|Создает объект типа `max_variable_size`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание:|
|-|-|
|[allocated](#allocated)|Увеличивает счетчик выделенных блоков памяти.|
|[deallocated](#deallocated)|Уменьшает счетчик выделенных блоков памяти.|
|[full](#full)|Возвращает значение, указывающее, следует ли добавить в свободный список дополнительные блоки памяти.|
|[released](#released)|Уменьшает количество блоков памяти в свободном списке.|
|[saved](#saved)|Увеличивает количество блоков памяти в свободном списке.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="allocated"></a>  max_variable_size::allocated

Увеличивает счетчик выделенных блоков памяти.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*_Nx*|Значение приращения.|

### <a name="remarks"></a>Примечания

Эта функция-член добавляет *_Nx* к сохраненному значению `_Nallocs`. Эта функция-член вызывается после каждого успешного вызова со стороны `cache_freelist::allocate` оператору **новый**. Аргумент *_Nx* — количество блоков памяти в блоке, выделяемом оператором **новый**.

## <a name="deallocated"></a>  max_variable_size::deallocated

Уменьшает счетчик выделенных блоков памяти.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*_Nx*|Значение приращения.|

### <a name="remarks"></a>Примечания

Функция-член вычитает *_Nx* из сохраненного значения `_Nallocs`. Эта функция-член вызывается после каждого вызова со стороны `cache_freelist::deallocate` оператору **удалить**. Аргумент *_Nx* — количество блоков памяти в блоке, который освобождается оператором **удалить**.

## <a name="full"></a>  max_variable_size::full

Возвращает значение, указывающее, следует ли добавить в свободный список дополнительные блоки памяти.

```cpp
bool full();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если `_Nallocs / 16 + 16 <= _Nblocks`.

### <a name="remarks"></a>Примечания

Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращает **true**, `deallocate` помещает блок памяти в свободный список; если он возвращает false, `deallocate` вызывает оператор **удалить** для освобождения блока.

## <a name="max_variable_size"></a>  max_variable_size::max_variable_size

Создает объект типа `max_variable_size`.

```cpp
max_variable_size();
```

### <a name="remarks"></a>Примечания

Конструктор инициализирует сохраненные значения `_Nblocks` и `_Nallocs` нулями.

## <a name="released"></a>  max_variable_size::released

Уменьшает количество блоков памяти в свободном списке.

```cpp
void released();
```

### <a name="remarks"></a>Примечания

Эта функция-член уменьшает хранимое значение `_Nblocks`. Функция-член `released` текущего класса max вызывается `cache_freelist::allocate` каждый раз при удалении блока памяти из свободного списка.

## <a name="saved"></a>  max_variable_size::saved

Увеличивает количество блоков памяти в свободном списке.

```cpp
void saved();
```

### <a name="remarks"></a>Примечания

Эта функция-член увеличивает хранимое значение `_Nblocks`. Она вызывается `cache_freelist::deallocate` каждый раз при помещении блока памяти в свободный список.

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)<br/>
