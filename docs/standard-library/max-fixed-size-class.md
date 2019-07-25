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
ms.openlocfilehash: bbc39a169f9a4bbac3e78b208b3a1a31e4e30ff2
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456367"
---
# <a name="maxfixedsize-class"></a>Класс max_fixed_size

Описывает объект [max class](../standard-library/allocators-header.md), который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) определенным значением.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Max>
class max_fixed_size
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Max*|Класс max, который определяет максимальное количество элементов для хранения в `freelist`.|

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[max_fixed_size](#max_fixed_size)|Создает объект типа `max_fixed_size`.|

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
|-|-|
|[allocated](#allocated)|Увеличивает счетчик выделенных блоков памяти.|
|[deallocated](#deallocated)|Уменьшает счетчик выделенных блоков памяти.|
|[full](#full)|Возвращает значение, указывающее, следует ли добавить в свободный список дополнительные блоки памяти.|
|[released](#released)|Уменьшает количество блоков памяти в свободном списке.|
|[saved](#saved)|Увеличивает количество блоков памяти в свободном списке.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="allocated"></a>  max_fixed_size::allocated

Увеличивает счетчик выделенных блоков памяти.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*_Nx*|Значение приращения.|

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Эта функция-член вызывается после каждого успешного вызова `cache_freelist::allocate` оператором **New**. Аргумент *_Nx* — это количество блоков памяти в блоке, выделенном оператором **New**.

## <a name="deallocated"></a>  max_fixed_size::deallocated

Уменьшает счетчик выделенных блоков памяти.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*_Nx*|Значение приращения.|

### <a name="remarks"></a>Примечания

Эта функция-член ничего не делает. Эта функция-член вызывается после каждого вызова `cache_freelist::deallocate` оператором **Delete**. Аргумент *_Nx* — это количество блоков памяти в блоке, освобожденных оператором **Delete**.

## <a name="full"></a>  max_fixed_size::full

Возвращает значение, указывающее, следует ли добавить в свободный список дополнительные блоки памяти.

```cpp
bool full();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если `Max <= _Nblocks`; в противном случае — **значение false**.

### <a name="remarks"></a>Примечания

Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращает **значение true**, `deallocate` блок памяти помещается в свободный список; если возвращается значение false, `deallocate` вызывает оператор **Delete** для освобождения блока.

## <a name="max_fixed_size"></a>  max_fixed_size::max_fixed_size

Создает объект типа `max_fixed_size`.

```cpp
max_fixed_size();
```

### <a name="remarks"></a>Примечания

Конструктор инициализирует сохраненное значение `_Nblocks` нулем.

## <a name="released"></a>  max_fixed_size::released

Уменьшает количество блоков памяти в свободном списке.

```cpp
void released();
```

### <a name="remarks"></a>Примечания

Уменьшает хранимое значение `_Nblocks`. Функция-член `released` текущего класса [max](../standard-library/allocators-header.md) вызывается `cache_freelist::allocate` каждый раз при удалении блока памяти из свободного списка.

## <a name="saved"></a>  max_fixed_size::saved

Увеличивает количество блоков памяти в свободном списке.

```cpp
void saved();
```

### <a name="remarks"></a>Примечания

Эта функция-член увеличивает хранимое значение `_Nblocks`. Она вызывается `cache_freelist::deallocate` каждый раз при помещении блока памяти в свободный список.

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)
