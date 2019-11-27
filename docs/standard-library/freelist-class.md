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
ms.openlocfilehash: e37b2371238211033d6a8a0847a41677b4e908a2
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688044"
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
|*SZ*|Число элементов в массиве, которые нужно выделить.|
|*Max*|Класс max, представляющий максимальное количество элементов, которые необходимо сохранить в свободном списке. Классом max может быть [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md) или [max_variable_size](../standard-library/max-variable-size-class.md).|

## <a name="remarks"></a>Заметки

Этот шаблон класса управляет списком блоков памяти размером *SZ* с максимальной длиной списка, определяемой классом Max, который передается *Max*.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[freelist](#freelist)|Создает объект типа `freelist`.|

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
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

### <a name="remarks"></a>Заметки

## <a name="pop"></a>  freelist::pop

Удаляет первый блок памяти из свободного списка.

```cpp
void *pop();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на блок памяти, удаленный из списка.

### <a name="remarks"></a>Заметки

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

**значение true** , если функция `full` класса max Возвращает **значение false**. в противном случае функция `push` возвращает **значение false**.

### <a name="remarks"></a>Заметки

Если функция `full` класса max Возвращает **значение false**, эта функция-член добавляет блок памяти, на который указывает *ptr* , в заголовок списка.

## <a name="see-also"></a>См. также

[\<allocators>](../standard-library/allocators-header.md)
