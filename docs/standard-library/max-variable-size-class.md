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
ms.openlocfilehash: f8b3c61676f784bf9369c22b5db97d7b251f7ac6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447286"
---
# <a name="maxvariablesize-class"></a>Класс max_variable_size

Описывает объект [max class](../standard-library/allocators-header.md), который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) до значения, приблизительно пропорционального количеству выделенных блоков памяти.

## <a name="syntax"></a>Синтаксис

```cpp
class max_variable_size
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[max_variable_size](#max_variable_size)|Создает объект типа `max_variable_size`.|

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

## <a name="allocated"></a>  max_variable_size::allocated

Увеличивает счетчик выделенных блоков памяти.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*_Nx*|Значение приращения.|

### <a name="remarks"></a>Примечания

Эта функция члена добавляет *_Nx* к сохраненному значению `_Nallocs`. Эта функция-член вызывается после каждого успешного вызова `cache_freelist::allocate` оператором **New**. Аргумент *_Nx* — это количество блоков памяти в блоке, выделенном оператором **New**.

## <a name="deallocated"></a>  max_variable_size::deallocated

Уменьшает счетчик выделенных блоков памяти.

```cpp
void deallocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*_Nx*|Значение приращения.|

### <a name="remarks"></a>Примечания

Функция члена вычитает *_Nx* из сохраненного значения `_Nallocs`. Эта функция-член вызывается после каждого вызова `cache_freelist::deallocate` оператором **Delete**. Аргумент *_Nx* — это количество блоков памяти в блоке, освобожденных оператором **Delete**.

## <a name="full"></a>  max_variable_size::full

Возвращает значение, указывающее, следует ли добавить в свободный список дополнительные блоки памяти.

```cpp
bool full();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если `_Nallocs / 16 + 16 <= _Nblocks`.

### <a name="remarks"></a>Примечания

Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращает **значение true**, `deallocate` блок памяти помещается в свободный список; если возвращается значение false, `deallocate` вызывает оператор **Delete** для освобождения блока.

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

[\<allocators>](../standard-library/allocators-header.md)
