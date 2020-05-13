---
title: Класс max_none
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
helpviewer_keywords:
- stdext::max_none
- stdext::max_none [C++], allocated
- stdext::max_none [C++], deallocated
- stdext::max_none [C++], full
- stdext::max_none [C++], released
- stdext::max_none [C++], saved
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
ms.openlocfilehash: c49ceec72be62d8ff3125f04d97bbb6952501677
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370982"
---
# <a name="max_none-class"></a>Класс max_none

Описывает объект [max class](../standard-library/allocators-header.md), который ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md) нулем.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Max>
class max_none
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Макс*|Класс max, который определяет максимальное количество элементов для хранения в `freelist`.|

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

## <a name="max_noneallocated"></a><a name="allocated"></a>max_none::выделено

Увеличивает счетчик выделенных блоков памяти.

```cpp
void allocated(std::size_t _Nx = 1);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*_Nx*|Значение приращения.|

### <a name="remarks"></a>Remarks

Эта функция-член ничего не делает. Оно вызвано после каждого `cache_freelist::allocate` успешного звонока к оператору **новому**. Аргументом *_Nx* является количество блоков памяти в блоке, выделенном оператором **новым.**

## <a name="max_nonedeallocated"></a><a name="deallocated"></a>max_none::dвыделено

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

## <a name="max_nonefull"></a><a name="full"></a>max_none::полный

Возвращает значение, указывающее, следует ли добавить дополнительные блоки памяти для свободного списка.

```cpp
bool full();
```

### <a name="return-value"></a>Возвращаемое значение

Эта функция члена всегда **возвращается верно**.

### <a name="remarks"></a>Remarks

Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращается `deallocate` **верно,** помещает блок памяти в свободный список; если он возвращает `deallocate` **ложные,** вызовы оператора **удалить,** чтобы разблокировать блок.

## <a name="max_nonereleased"></a><a name="released"></a>max_none::выпущен

Уменьшает количество блоков памяти в свободном списке.

```cpp
void released();
```

### <a name="remarks"></a>Remarks

Эта функция-член ничего не делает. Функция-член `released` текущего класса max вызывается `cache_freelist::allocate` каждый раз при удалении блока памяти из свободного списка.

## <a name="max_nonesaved"></a><a name="saved"></a>max_none:::сохранено

Увеличивает количество блоков памяти в свободном списке.

```cpp
void saved();
```

### <a name="remarks"></a>Remarks

Эта функция-член ничего не делает. Вызывается методом `cache_freelist::deallocate` каждый раз, когда он помещает блок памяти свободного списка.

## <a name="see-also"></a>См. также раздел

[\<>-подлатыватели](../standard-library/allocators-header.md)
