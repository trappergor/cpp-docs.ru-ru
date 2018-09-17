---
title: Класс freelist | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- allocators/stdext::freelist
- allocators/stdext::freelist::pop
- allocators/stdext::freelist::push
dev_langs:
- C++
helpviewer_keywords:
- stdext::freelist
- stdext::freelist [C++], pop
- stdext::freelist [C++], push
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae7e56fd33de888ad31a24ad1e3130acc96daa28
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702834"
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
|*sz*|Число элементов в массиве, которые нужно выделить.|
|*Max*|Класс max, представляющий максимальное количество элементов, которые необходимо сохранить в свободном списке. Классом max может быть [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md) или [max_variable_size](../standard-library/max-variable-size-class.md).|

## <a name="remarks"></a>Примечания

Этот класс шаблона управляет списком блоков памяти размером *Sz* с максимальной длиной списка, которая определяется классом max, переданный *Max*.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[freelist](#freelist)|Создает объект типа `freelist`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[pop](#pop)|Удаляет первый блок памяти из свободного списка.|
|[push](#push)|Добавляет блок памяти в список.|

## <a name="requirements"></a>Требования

**Заголовок:** \<allocators>

**Пространство имен:** stdext

## <a name="freelist"></a>  freelist::freelist

Создает объект типа `freelist`.

```cpp
freelist();
```

### <a name="remarks"></a>Примечания

## <a name="pop"></a>  freelist::pop

Удаляет первый блок памяти из свободного списка.

```cpp
void *pop();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на блок памяти, удаленный из списка.

### <a name="remarks"></a>Примечания

Функция-член возвращает значение NULL, если список пуст. В противном случае удаляет первый блок памяти из списка.

## <a name="push"></a>  freelist::push

Добавляет блок памяти в список.

```cpp
bool push(void* ptr);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*ptr*|Указатель на блок памяти, которые необходимо добавить в свободный список.|

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если `full` функция класса max возвращает **false**; в противном случае `push` возвращает **false**.

### <a name="remarks"></a>Примечания

Если `full` функция класса max возвращает **false**, эта функция-член добавляет блок памяти, на которые указывают *ptr* в начало списка.

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)<br/>
