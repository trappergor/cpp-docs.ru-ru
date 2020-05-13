---
title: Класс max_unbounded
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::max_unbounded
- allocators/stdext::max_unbounded::allocated
- allocators/stdext::max_unbounded::deallocated
- allocators/stdext::max_unbounded::full
- allocators/stdext::max_unbounded::released
- allocators/stdext::max_unbounded::saved
helpviewer_keywords:
- stdext::max_unbounded
- stdext::max_unbounded [C++], allocated
- stdext::max_unbounded [C++], deallocated
- stdext::max_unbounded [C++], full
- stdext::max_unbounded [C++], released
- stdext::max_unbounded [C++], saved
ms.assetid: e34627a9-c231-4031-a483-cbb0514fff46
ms.openlocfilehash: fbc4351297ab8a3cc90a2a77fa31c3b134f10eab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370996"
---
# <a name="max_unbounded-class"></a>Класс max_unbounded

Описывает объект [max class](../standard-library/allocators-header.md), который не ограничивает максимальную длину объекта [freelist](../standard-library/freelist-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
class max_unbounded
```

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

## <a name="max_unboundedallocated"></a><a name="allocated"></a>max_unbounded::выделено

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

## <a name="max_unboundeddeallocated"></a><a name="deallocated"></a>max_unbounded::dвыделение

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

## <a name="max_unboundedfull"></a><a name="full"></a>max_unbounded::full

Возвращает значение, указывающее, следует ли добавить дополнительные блоки памяти для свободного списка.

```cpp
bool full();
```

### <a name="return-value"></a>Возвращаемое значение

Функция участника всегда возвращает **ложное**.

### <a name="remarks"></a>Remarks

Эта функция-член вызывается `cache_freelist::deallocate`. Если вызов возвращается `deallocate` **верно,** помещает блок памяти в свободный список; если он возвращает `deallocate` ложные, вызовы оператора **удалить,** чтобы разблокировать блок.

## <a name="max_unboundedreleased"></a><a name="released"></a>max_unbounded::выпущен

Уменьшает количество блоков памяти в свободном списке.

```cpp
void released();
```

### <a name="remarks"></a>Remarks

Эта функция-член ничего не делает. Функция-член `released` текущего класса max вызывается `cache_freelist::allocate` каждый раз при удалении блока памяти из свободного списка.

## <a name="max_unboundedsaved"></a><a name="saved"></a>max_unbounded::сохранено

Увеличивает количество блоков памяти в свободном списке.

```cpp
void saved();
```

### <a name="remarks"></a>Remarks

Эта функция-член ничего не делает. Вызывается методом `cache_freelist::deallocate` каждый раз, когда он помещает блок памяти свободного списка.

## <a name="see-also"></a>См. также раздел

[\<>-подлатыватели](../standard-library/allocators-header.md)
