---
title: Класс max_none | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
dev_langs:
- C++
helpviewer_keywords:
- stdext::max_none
- stdext::max_none [C++], allocated
- stdext::max_none [C++], deallocated
- stdext::max_none [C++], full
- stdext::max_none [C++], released
- stdext::max_none [C++], saved
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 44981141be5bfb4f18cb278e724ab905aebcc5cf
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964175"
---
# <a name="maxnone-class"></a>Класс max_none

Описывает объект [max class](../standard-library/allocators-header.md), который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) нулем.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Max>
class max_none
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*Max*|Класс max, который определяет максимальное количество элементов для хранения в `freelist`.|

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

## <a name="allocated"></a>  max_none::allocated

Увеличивает счетчик выделенных блоков памяти.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*_Nx*|Значение приращения.|

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Вызывается после каждого успешного вызова со стороны `cache_freelist::allocate` оператору **новый**. Аргумент *_Nx* — количество блоков памяти в блоке, выделяемом оператором **новый**.

## <a name="deallocated"></a>  max_none::deallocated

Уменьшает счетчик выделенных блоков памяти.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*_Nx*|Значение приращения.|

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Эта функция-член вызывается после каждого вызова со стороны `cache_freelist::deallocate` оператору **удалить**. Аргумент *_Nx* — количество блоков памяти в блоке, который освобождается оператором **удалить**.

## <a name="full"></a>  max_none::full

Возвращает значение, указывающее, следует ли добавить дополнительные блоки памяти для свободного списка.

```cpp
bool full();
```

### <a name="return-value"></a>Возвращаемое значение

Эта функция-член всегда возвращает **true**.

### <a name="remarks"></a>Примечания

Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращает **true**, `deallocate` помещает блок памяти в свободный список; если он возвращает false, `deallocate` вызывает оператор **удалить** для освобождения блока.

## <a name="released"></a>  max_none::released

Уменьшает количество блоков памяти в свободном списке.

```cpp
void released();
```

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Функция-член `released` текущего класса max вызывается `cache_freelist::allocate` каждый раз при удалении блока памяти из свободного списка.

## <a name="saved"></a>  max_none::saved

Увеличивает количество блоков памяти в свободном списке.

```cpp
void saved();
```

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Вызывается методом `cache_freelist::deallocate` каждый раз, когда он помещает блок памяти свободного списка.

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)<br/>
