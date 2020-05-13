---
title: Класс max_fixed_size
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_fixed_size
- allocators/stdext::max_fixed_size::allocated
- allocators/stdext::max_fixed_size::deallocated
- allocators/stdext::max_fixed_size::full
- allocators/stdext::max_fixed_size::released
- allocators/stdext::max_fixed_size::saved
helpviewer_keywords:
- stdext::max_fixed_size
- stdext::max_fixed_size [C++], allocated
- stdext::max_fixed_size [C++], deallocated
- stdext::max_fixed_size [C++], full
- stdext::max_fixed_size [C++], released
- stdext::max_fixed_size [C++], saved
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
ms.openlocfilehash: 7f75dd71caa3cfcfec19264b1da62c6d47a3e01d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371008"
---
# <a name="max_fixed_size-class"></a>Класс max_fixed_size

Описывает объект [max class](../standard-library/allocators-header.md), который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) определенным значением.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Max>
class max_fixed_size
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Макс*|Класс max, который определяет максимальное количество элементов для хранения в `freelist`.|

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[max_fixed_size](#max_fixed_size)|Создает объект типа `max_fixed_size`.|

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

## <a name="max_fixed_sizeallocated"></a><a name="allocated"></a>max_fixed_size::выделено

Увеличивает счетчик выделенных блоков памяти.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*_Nx*|Значение приращения.|

### <a name="remarks"></a>Remarks

Эта функция-член ничего не делает. Эта функция участника вызывается после `cache_freelist::allocate` каждого успешного вызова оператором **нового**. Аргументом *_Nx* является количество блоков памяти в блоке, выделенном оператором **новым.**

## <a name="max_fixed_sizedeallocated"></a><a name="deallocated"></a>max_fixed_size::dвыделено

Уменьшает счетчик выделенных блоков памяти.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*_Nx*|Значение приращения.|

### <a name="remarks"></a>Remarks

Эта функция-член ничего не делает. Эта функция участника вызывается `cache_freelist::deallocate` после каждого вызова оператором **удаления.** Аргументом *_Nx* является количество блоков памяти в сделке, размещенной оператором, **удаляется.**

## <a name="max_fixed_sizefull"></a><a name="full"></a>max_fixed_size::full

Возвращает значение, указывающее, следует ли добавить дополнительные блоки памяти для свободного списка.

```cpp
bool full();
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если `Max <= _Nblocks`; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращается `deallocate` **верно,** помещает блок памяти в свободный список; если он возвращает `deallocate` ложные, вызовы оператора **удалить,** чтобы разблокировать блок.

## <a name="max_fixed_sizemax_fixed_size"></a><a name="max_fixed_size"></a>max_fixed_size::max_fixed_size

Создает объект типа `max_fixed_size`.

```cpp
max_fixed_size();
```

### <a name="remarks"></a>Remarks

Конструктор инициализирует сохраненное значение `_Nblocks` нулем.

## <a name="max_fixed_sizereleased"></a><a name="released"></a>max_fixed_size::выпущен

Уменьшает количество блоков памяти в свободном списке.

```cpp
void released();
```

### <a name="remarks"></a>Remarks

Уменьшает хранимое значение `_Nblocks`. Функция `released` участника текущего [класса max](../standard-library/allocators-header.md) `cache_freelist::allocate` вызывается всякий раз, когда она удаляет блок памяти из свободного списка.

## <a name="max_fixed_sizesaved"></a><a name="saved"></a>max_fixed_size::сохранено

Увеличивает количество блоков памяти в свободном списке.

```cpp
void saved();
```

### <a name="remarks"></a>Remarks

Эта функция-член увеличивает хранимое значение `_Nblocks`. Она вызывается `cache_freelist::deallocate` каждый раз при помещении блока памяти в свободный список.

## <a name="see-also"></a>См. также раздел

[\<>-подлатыватели](../standard-library/allocators-header.md)
