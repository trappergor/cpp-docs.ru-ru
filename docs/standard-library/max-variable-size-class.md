---
title: Класс max_variable_size
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_variable_size
- allocators/stdext::max_variable_size::allocated
- allocators/stdext::max_variable_size::deallocated
- allocators/stdext::max_variable_size::full
- allocators/stdext::max_variable_size::released
- allocators/stdext::max_variable_size::saved
helpviewer_keywords:
- stdext::max_variable_size
- stdext::max_variable_size [C++], allocated
- stdext::max_variable_size [C++], deallocated
- stdext::max_variable_size [C++], full
- stdext::max_variable_size [C++], released
- stdext::max_variable_size [C++], saved
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
ms.openlocfilehash: 79e37d8c464a009e4a5196aeacc8d4a718e355b9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370971"
---
# <a name="max_variable_size-class"></a>Класс max_variable_size

Описывает объект [max class](../standard-library/allocators-header.md), который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) до значения, приблизительно пропорционального количеству выделенных блоков памяти.

## <a name="syntax"></a>Синтаксис

```cpp
class max_variable_size
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[max_variable_size](#max_variable_size)|Создает объект типа `max_variable_size`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[allocated](#allocated)|Увеличивает счетчик выделенных блоков памяти.|
|[Освобождена](#deallocated)|Уменьшает счетчик выделенных блоков памяти.|
|[Полный](#full)|Возвращает значение, указывающее, следует ли добавить дополнительные блоки памяти для свободного списка.|
|[Выпущен](#released)|Уменьшает количество блоков памяти в свободном списке.|
|[saved](#saved)|Увеличивает количество блоков памяти в свободном списке.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="max_variable_sizeallocated"></a><a name="allocated"></a>max_variable_size::выделено

Увеличивает счетчик выделенных блоков памяти.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*_Nx*|Значение приращения.|

### <a name="remarks"></a>Remarks

Эта функция *_Nx* члена добавляет _Nx `_Nallocs`к сохраненной стоимости. Эта функция участника вызывается после `cache_freelist::allocate` каждого успешного вызова оператором **нового**. Аргументом *_Nx* является количество блоков памяти в блоке, выделенном оператором **новым.**

## <a name="max_variable_sizedeallocated"></a><a name="deallocated"></a>max_variable_size::dвыделен

Уменьшает счетчик выделенных блоков памяти.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*_Nx*|Значение приращения.|

### <a name="remarks"></a>Remarks

Функция участника вычитает *_Nx* из `_Nallocs`сохраненного значения. Эта функция участника вызывается `cache_freelist::deallocate` после каждого вызова оператором **удаления.** Аргументом *_Nx* является количество блоков памяти в сделке, размещенной оператором, **удаляется.**

## <a name="max_variable_sizefull"></a><a name="full"></a>max_variable_size::полный

Возвращает значение, указывающее, следует ли добавить дополнительные блоки памяти для свободного списка.

```cpp
bool full();
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `_Nallocs / 16 + 16 <= _Nblocks`.

### <a name="remarks"></a>Remarks

Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращается `deallocate` **верно,** помещает блок памяти в свободный список; если он возвращает `deallocate` ложные, вызовы оператора **удалить,** чтобы разблокировать блок.

## <a name="max_variable_sizemax_variable_size"></a><a name="max_variable_size"></a>max_variable_size::max_variable_size

Создает объект типа `max_variable_size`.

```cpp
max_variable_size();
```

### <a name="remarks"></a>Remarks

Конструктор инициализирует сохраненные значения `_Nblocks` и `_Nallocs` нулями.

## <a name="max_variable_sizereleased"></a><a name="released"></a>max_variable_size::выпущен

Уменьшает количество блоков памяти в свободном списке.

```cpp
void released();
```

### <a name="remarks"></a>Remarks

Эта функция-член уменьшает хранимое значение `_Nblocks`. Функция-член `released` текущего класса max вызывается `cache_freelist::allocate` каждый раз при удалении блока памяти из свободного списка.

## <a name="max_variable_sizesaved"></a><a name="saved"></a>max_variable_size::сохранено

Увеличивает количество блоков памяти в свободном списке.

```cpp
void saved();
```

### <a name="remarks"></a>Remarks

Эта функция-член увеличивает хранимое значение `_Nblocks`. Она вызывается `cache_freelist::deallocate` каждый раз при помещении блока памяти в свободный список.

## <a name="see-also"></a>См. также раздел

[\<>-подлатыватели](../standard-library/allocators-header.md)
