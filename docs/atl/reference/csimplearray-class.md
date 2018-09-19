---
title: Класс CSimpleArray | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::Add
- ATLSIMPCOLL/ATL::CSimpleArray::Find
- ATLSIMPCOLL/ATL::CSimpleArray::GetData
- ATLSIMPCOLL/ATL::CSimpleArray::GetSize
- ATLSIMPCOLL/ATL::CSimpleArray::Remove
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleArray::SetAtIndex
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArray class
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5603327e7bdc32d9b760fc25160543c682e6f4f4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054510"
---
# <a name="csimplearray-class"></a>Класс CSimpleArray

Этот класс предоставляет методы для управления простого массива.

## <a name="syntax"></a>Синтаксис

```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>
class CSimpleArray
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Тип данных для хранения в массиве.

*TEqual*<br/>
Объект признак, определяющий тест на равенство для элементов типа *T*.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSimpleArray::CSimpleArray](#csimplearray)|Конструктор для простого массива.|
|[CSimpleArray:: ~ CSimpleArray](#dtor)|Деструктор для простого массива.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSimpleArray::Add](#add)|Добавляет новый элемент в массив.|
|[CSimpleArray::Find](#find)|Поиск элемента в массиве.|
|[CSimpleArray::GetData](#getdata)|Возвращает указатель на данные, хранящиеся в массиве.|
|[CSimpleArray::GetSize](#getsize)|Возвращает количество элементов, содержащихся в массиве.|
|[CSimpleArray::Remove](#remove)|Удаляет заданный элемент из массива.|
|[CSimpleArray::RemoveAll](#removeall)|Удаляет все элементы из массива.|
|[CSimpleArray::RemoveAt](#removeat)|Удаляет указанный элемент из массива.|
|[CSimpleArray::SetAtIndex](#setatindex)|Присваивает заданному элементу в массиве.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[CSimpleArray::operator\[\]](#operator_at)|Получает элемент из массива.|
|[CSimpleArray::operator =](#operator_eq)|Оператор присвоения.|  

## <a name="remarks"></a>Примечания

`CSimpleArray` Предоставляет методы для создания и управления простого массива, заданного типа `T`.

Параметр `TEqual` предоставляет средства определения функцию проверки на равенство для двух элементов типа `T`. Путем создания класса, аналогичную [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md), можно изменить поведение проверки на равенство для любого заданного массива. Например при работе с массив указателей, его можно использовать для определения равенства, как в зависимости от значения, которые ссылаются на указатели. Реализация по умолчанию использует **operator=()**.

Оба `CSimpleArray` и [CSimpleMap](../../atl/reference/csimplemap-class.md) предназначены для небольшого числа элементов. [CAtlArray](../../atl/reference/catlarray-class.md) и [CAtlMap](../../atl/reference/catlmap-class.md) следует использовать, если массив содержит большое количество элементов.

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpcoll.h

## <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#86](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]

##  <a name="add"></a>  CSimpleArray::Add

Добавляет новый элемент в массив.

```
BOOL Add(const T& t);
```

### <a name="parameters"></a>Параметры

*t*<br/>
Элемент, добавляемый в массив.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если элемент успешно добавлен в массив, значение FALSE в противном случае.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#87](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]

##  <a name="csimplearray"></a>  CSimpleArray::CSimpleArray

Конструктор для объекта-массива.

```
CSimpleArray(const CSimpleArray<T, TEqual>& src);
CSimpleArray();
```

### <a name="parameters"></a>Параметры

*src*<br/>
Существующий объект `CSimpleArray`.

### <a name="remarks"></a>Примечания

Инициализирует данные-члены, создать новую пустую `CSimpleArray` объекта или копии существующего `CSimpleArray` объекта.

##  <a name="dtor"></a>  CSimpleArray:: ~ CSimpleArray

Деструктор

```
~CSimpleArray();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

##  <a name="find"></a>  CSimpleArray::Find

Поиск элемента в массиве.

```
int Find(const T& t) const;
```

### <a name="parameters"></a>Параметры

*t*<br/>
Элемент, который требуется найти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает индекс найденного элемента, или значение -1, если элемент не найден.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#88](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]

##  <a name="getdata"></a>  CSimpleArray::GetData

Возвращает указатель на данные, хранящиеся в массиве.

```
T* GetData() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на данные в массиве.

##  <a name="getsize"></a>  CSimpleArray::GetSize

Возвращает количество элементов, содержащихся в массиве.

```
int GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество элементов, содержащихся в массиве.

##  <a name="operator_at"></a>  CSimpleArray::operator \[\]

Получает элемент из массива.

```
T& operator[](int nindex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс элемента.

### <a name="return-value"></a>Возвращаемое значение

Возвращает элемент массива ссылается *nIndex*.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#89](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]

##  <a name="operator_eq"></a>  CSimpleArray::operator =

Оператор присвоения.

```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```

### <a name="parameters"></a>Параметры

*src*<br/>
Массив для копирования.

### <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на обновленный `CSimpleArray` объекта.

### <a name="remarks"></a>Примечания

Копирует все элементы из `CSimpleArray` объект, упоминаемый в *src* в текущий объект массива, заменив все существующие данные.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#90](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]

##  <a name="remove"></a>  CSimpleArray::Remove

Удаляет заданный элемент из массива.

```
BOOL Remove(const T& t);
```

### <a name="parameters"></a>Параметры

*t*<br/>
Элемент, удаляемый из массива.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если элемент найден и удален, и FALSE в противном случае.

### <a name="remarks"></a>Примечания

Когда элемент удаляется, оставшиеся элементы в массиве нумеруются для заполнения пустого пространства.

##  <a name="removeall"></a>  CSimpleArray::RemoveAll

Удаляет все элементы из массива.

```
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Удаляет все элементы, которые в настоящее время хранятся в массиве.

##  <a name="removeat"></a>  CSimpleArray::RemoveAt

Удаляет указанный элемент из массива.

```
BOOL RemoveAtint nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс, указывающий на элемент для удаления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если элемент был удален, и FALSE, если индекс был недопустимым.

### <a name="remarks"></a>Примечания

Когда элемент удаляется, оставшиеся элементы в массиве нумеруются для заполнения пустого пространства.

##  <a name="setatindex"></a>  CSimpleArray::SetAtIndex

Значение указанного элемента в массиве.

```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс элемента, который требуется изменить.

*t*<br/>
Значение, присваиваемое указанному элементу.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE при успешном выполнении и FALSE, если индекс не является допустимым.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
