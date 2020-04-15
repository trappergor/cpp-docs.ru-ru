---
title: Класс freelist
ms.date: 11/04/2016
f1_keywords:
- allocators/stdext::freelist
- allocators/stdext::freelist::pop
- allocators/stdext::freelist::push
helpviewer_keywords:
- stdext::freelist
- stdext::freelist [C++], pop
- stdext::freelist [C++], push
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
ms.openlocfilehash: 712c1f1638b954d1580eb527dd9eab7401917517
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317204"
---
# <a name="freelist-class"></a>Класс freelist

Управляет списком блоков памяти.

## <a name="syntax"></a>Синтаксис

```cpp
template <std::size_t Sz, class Max>
class freelist : public Max
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Sz*|Число выделяемых элементов в массиве.|
|*Макс*|Класс max, представляющий максимальное количество элементов, которые необходимо сохранить в свободном списке. Классом max может быть [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md) или [max_variable_size](../standard-library/max-variable-size-class.md).|

## <a name="remarks"></a>Remarks

Этот шаблон класса управляет списком блоков памяти размера *Sz* с максимальной длиной списка, определяемого классом max, пройденым в *Max.*

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[freelist](#freelist)|Создает объект типа `freelist`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Поп](#pop)|Удаляет первый блок памяти из свободного списка.|
|[Нажмите](#push)|Добавляет блок памяти в список.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="freelistfreelist"></a><a name="freelist"></a>свободный лист::фрилист

Создает объект типа `freelist`.

```cpp
freelist();
```

### <a name="remarks"></a>Remarks

## <a name="freelistpop"></a><a name="pop"></a>фрилист::pop

Удаляет первый блок памяти из свободного списка.

```cpp
void *pop();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на блок памяти, удаленный из списка.

### <a name="remarks"></a>Remarks

Функция участника возвращает NULL, если список пуст. В противном случае удаляет первый блок памяти из списка.

## <a name="freelistpush"></a><a name="push"></a>фрилист::pуш

Добавляет блок памяти в список.

```cpp
bool push(void* ptr);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Ptr*|Указатель на блок памяти, которые необходимо добавить в свободный список.|

### <a name="return-value"></a>Возвращаемое значение

**верно,** `full` если функция макс класса **возвращается ложно;** в противном случае функция возвращает `push` **ложную.**

### <a name="remarks"></a>Remarks

Если `full` функция max class возвращается **ложно,** эта функция-член добавляет блок памяти, на который указывает *ptr* к главе списка.

## <a name="see-also"></a>См. также раздел

[\<>-подлатыватели](../standard-library/allocators-header.md)
