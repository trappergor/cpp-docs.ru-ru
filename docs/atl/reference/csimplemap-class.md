---
title: Класс CSimpleMap | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayElementType
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayKeyType
- ATLSIMPCOLL/ATL::CSimpleMap::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::Add
- ATLSIMPCOLL/ATL::CSimpleMap::FindKey
- ATLSIMPCOLL/ATL::CSimpleMap::FindVal
- ATLSIMPCOLL/ATL::CSimpleMap::GetKeyAt
- ATLSIMPCOLL/ATL::CSimpleMap::GetSize
- ATLSIMPCOLL/ATL::CSimpleMap::GetValueAt
- ATLSIMPCOLL/ATL::CSimpleMap::Lookup
- ATLSIMPCOLL/ATL::CSimpleMap::Remove
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleMap::ReverseLookup
- ATLSIMPCOLL/ATL::CSimpleMap::SetAt
- ATLSIMPCOLL/ATL::CSimpleMap::SetAtIndex
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMap class
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0fa2c3b421aa0aa60194f8ed949c023d78b70c2d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070306"
---
# <a name="csimplemap-class"></a>Класс CSimpleMap

Этот класс обеспечивает поддержку для массива простое сопоставление.

## <a name="syntax"></a>Синтаксис

```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>
class CSimpleMap
```

#### <a name="parameters"></a>Параметры

*TKey*<br/>
Тип ключа элемента.

*TVal*<br/>
Тип значения элемента.

*TEqual*<br/>
Объект признак, определяющий тест на равенство для элементов типа `T`.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|[CSimpleMap::_ArrayElementType](#_arrayelementtype)|TypeDef для типа значения.|
|[CSimpleMap::_ArrayKeyType](#_arraykeytype)|TypeDef для типа ключа.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CSimpleMap::CSimpleMap](#csimplemap)|Конструктор.|
|[CSimpleMap:: ~ CSimpleMap](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CSimpleMap::Add](#add)|Добавляет ключ и связанное значение в массив сопоставлений.|
|[CSimpleMap::FindKey](#findkey)|Находит указанный ключ.|
|[CSimpleMap::FindVal](#findval)|Находит указанное значение.|
|[CSimpleMap::GetKeyAt](#getkeyat)|Извлекает указанный ключ.|
|[CSimpleMap::GetSize](#getsize)|Возвращает число записей в массиве сопоставления.|
|[CSimpleMap::GetValueAt](#getvalueat)|Возвращает указанное значение.|
|[CSimpleMap::Lookup](#lookup)|Возвращает значение, связанное с указанным ключом.|
|[CSimpleMap::Remove](#remove)|Удаляет ключ и соответствующее значение.|
|[CSimpleMap::RemoveAll](#removeall)|Удаляет все ключи и значения.|
|[CSimpleMap::RemoveAt](#removeat)|Удаляет указанные ключ и соответствующее значение.|
|[CSimpleMap::ReverseLookup](#reverselookup)|Возвращает ключ, связанный с заданным значением.|
|[CSimpleMap::SetAt](#setat)|Задает значение, связанное с указанным ключом.|
|[CSimpleMap::SetAtIndex](#setatindex)|Задает указанные ключ и значение.|

## <a name="remarks"></a>Примечания

`CSimpleMap` предоставляет поддержку для любого заданного типа массива простое сопоставление `T`, управление массив неупорядоченные ключевые элементы и связанные с ними значения.

Параметр `TEqual` предоставляет средства определения функцию проверки на равенство для двух элементов типа `T`. Путем создания класса, аналогичную [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md), можно изменить поведение проверки на равенство для любого заданного массива. Например при работе с массив указателей, его можно использовать для определения равенства, как в зависимости от значения, которые ссылаются на указатели. Реализация по умолчанию использует **operator==()**.

Оба `CSimpleMap` и [CSimpleArray](../../atl/reference/csimplearray-class.md) предоставляются для совместимости с предыдущей ATL версий, более полный и эффективной реализации коллекции предоставляемые [CAtlArray](../../atl/reference/catlarray-class.md) и [ CAtlMap](../../atl/reference/catlmap-class.md).

В отличие от других коллекций карты в ATL и MFC этот класс реализуется с помощью простого массива и поиска lookup необходим линейный поиск. `CAtlMap` следует использовать, если массив содержит большое количество элементов.

## <a name="requirements"></a>Требования

**Заголовок:** atlsimpcoll.h

## <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]

##  <a name="add"></a>  CSimpleMap::Add

Добавляет ключ и связанное значение в массив сопоставлений.

```
BOOL Add(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ.

*Val*<br/>
Связанное значение.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если ключ и значение были успешно добавлен, и FALSE в противном случае.

### <a name="remarks"></a>Примечания

Каждая пара ключ-значение добавить сопоставление массива памяти освобождается и перераспределить, чтобы убедиться, что данные для каждого непрерывно всегда хранится причины. То есть второй ключевой элемент всегда сразу после первого ключа элемента в памяти и т. д.

##  <a name="_arrayelementtype"></a>  CSimpleMap::_ArrayElementType

Typedef для типа ключа.

```
typedef TVal _ArrayElementType;
```

##  <a name="_arraykeytype"></a>  CSimpleMap::_ArrayKeyType

Typedef для типа значения.

```
typedef TKey _ArrayKeyType;
```

##  <a name="csimplemap"></a>  CSimpleMap::CSimpleMap

Конструктор.

```
CSimpleMap();
```

### <a name="remarks"></a>Примечания

Инициализирует члены данных.

##  <a name="dtor"></a>  CSimpleMap:: ~ CSimpleMap

Деструктор

```
~CSimpleMap();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

##  <a name="findkey"></a>  CSimpleMap::FindKey

Находит указанный ключ.

```
int FindKey(const TKey& key) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ, который нужно найти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает индекс ключа, если объект найден, в противном случае возвращает значение -1.

##  <a name="findval"></a>  CSimpleMap::FindVal

Находит указанное значение.

```
int FindVal(const TVal& val) const;
```

### <a name="parameters"></a>Параметры

*Val*<br/>
Значение, которое требуется найти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает индекс значения, если он найден; в противном случае возвращает -1.

##  <a name="getkeyat"></a>  CSimpleMap::GetKeyAt

Получает ключ по указанному индексу.

```
TKey& GetKeyAt(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс возвращаемого ключевого поля.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ключ, который ссылается *nIndex*.

### <a name="remarks"></a>Примечания

Индекс, переданный *nIndex* должен быть допустимым для возвращаемого значения сделать его значимым.

##  <a name="getsize"></a>  CSimpleMap::GetSize

Возвращает число записей в массиве сопоставления.

```
int GetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает число записей (ключ и значение — одна запись) в массиве сопоставления.

##  <a name="getvalueat"></a>  CSimpleMap::GetValueAt

Получает значение по указанному индексу.

```
TVal& GetValueAt(int nIndex) const;
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс возвращаемого значения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, найденное по *nIndex*.

### <a name="remarks"></a>Примечания

Индекс, переданный *nIndex* должен быть допустимым для возвращаемого значения сделать его значимым.

##  <a name="lookup"></a>  CSimpleMap::Lookup

Возвращает значение, связанное с указанным ключом.

```
TVal Lookup(const TKey& key) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ.

### <a name="return-value"></a>Возвращаемое значение

Возвращает связанное значение. Если такой ключ не найден, значение NULL возвращается.

##  <a name="remove"></a>  CSimpleMap::Remove

Удаляет ключ и соответствующее значение.

```
BOOL Remove(const TKey& key);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если ключ и соответствующее значение, были успешно удален, и FALSE в противном случае.

##  <a name="removeall"></a>  CSimpleMap::RemoveAll

Удаляет все ключи и значения.

```
void RemoveAll();
```

### <a name="remarks"></a>Примечания

Удаляет все ключи и значения из массива объекта сопоставления.

##  <a name="removeat"></a>  CSimpleMap::RemoveAt

Удаляет ключ и связанное значение по указанному индексу.

```
BOOL RemoveAt(int nIndex);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс ключа и связанные значения для удаления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE в случае успеха, FALSE, если указанный индекс является недопустимый индекс.

##  <a name="reverselookup"></a>  CSimpleMap::ReverseLookup

Возвращает ключ, связанный с заданным значением.

```
TKey ReverseLookup(const TVal& val) const;
```

### <a name="parameters"></a>Параметры

*Val*<br/>
Значение.

### <a name="return-value"></a>Возвращаемое значение

Возвращает связанный ключ. Если такой ключ не найден, значение NULL возвращается.

##  <a name="setat"></a>  CSimpleMap::SetAt

Задает значение, связанное с указанным ключом.

```
BOOL SetAt(const TKey& key, const TVal& val);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ.

*Val*<br/>
Новое значение для назначения.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE, если ключ найден и значение было успешно изменен, и FALSE в противном случае.

##  <a name="setatindex"></a>  CSimpleMap::SetAtIndex

Задает ключ и значение по указанному индексу.

```
BOOL SetAtIndex(  
    int nIndex,
    const TKey& key,
    const TVal& val);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Индекс, ссылающиеся на ключ и значение, связывание для изменения.

*key*<br/>
Новый ключ.

*Val*<br/>
Новое значение.

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение TRUE при успешном выполнении и FALSE, если индекс не является допустимым.

### <a name="remarks"></a>Примечания

Обновляет ключ и значение, на которые указывают *nIndex*.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
