---
title: Класс cache_suballoc
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::cache_suballoc
- allocators/stdext::cache_suballoc::allocate
- allocators/stdext::cache_suballoc::deallocate
helpviewer_keywords:
- stdext::cache_suballoc
- stdext::cache_suballoc [C++], allocate
- stdext::cache_suballoc [C++], deallocate
ms.assetid: 9ea9c5e9-1dcc-45d0-b3a7-a56a93d88898
ms.openlocfilehash: 55860a65fc77f834ed699f3a5114768b7efdde6f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366729"
---
# <a name="cache_suballoc-class"></a>Класс cache_suballoc

Задает [распределитель блоков](../standard-library/allocators-header.md), который выделяет и освобождает блоки памяти одного размера.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Sz, size_t Nelts = 20>
class cache_suballoc
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Sz*|Число выделяемых элементов в массиве.|

## <a name="remarks"></a>Remarks

Магазины шаблонов cache_suballoc класса рассеяны блоки памяти в свободном списке с неограниченной длиной, используя `freelist<sizeof(Type), max_unbounded>`и субсидируя блоки памяти из большего фрагмента, выделенного с новым **оператором,** когда свободный список пуст.

Каждый `Sz * Nelts` кусок содержит байты пригодной для использования памяти и данные, которые **требуется новым оператором** и **оператором.** Выделенные участки памяти никогда не будут освобождены.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[cache_suballoc](#cache_suballoc)|Создает объект типа `cache_suballoc`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Выделить](#allocate)|Выделяет блок памяти.|
|[Освобождения](#deallocate)|Освобождает указанное число объектов из памяти, начиная с заданной позиции.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="cache_suballocallocate"></a><a name="allocate"></a>cache_suballoc::

Выделяет блок памяти.

```cpp
void *allocate(std::size_t count);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*count*|Число выделяемых элементов в массиве.|

### <a name="return-value"></a>Возвращаемое значение

Указатель на выделяемый объект.

### <a name="remarks"></a>Remarks

## <a name="cache_suballoccache_suballoc"></a><a name="cache_suballoc"></a>cache_suballoc::cache_suballoc

Создает объект типа `cache_suballoc`.

```cpp
cache_suballoc();
```

### <a name="remarks"></a>Remarks

## <a name="cache_suballocdeallocate"></a><a name="deallocate"></a>cache_suballoc::dраспределение

Освобождает указанное число объектов из памяти, начиная с заданной позиции.

```cpp
void deallocate(void* ptr, std::size_t count);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Ptr*|Указатель на первый объект, который должен быть освобожден из хранилища.|
|*count*|Количество объектов для освобождения из хранилища.|

### <a name="remarks"></a>Remarks

## <a name="see-also"></a>См. также раздел

[\<>-подлатыватели](../standard-library/allocators-header.md)
