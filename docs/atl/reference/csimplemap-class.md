---
title: "Класс CSimpleMap | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: c02ef1d9d3fafebf38abaaa55d77511f4476a02f
ms.lasthandoff: 02/24/2017

---
# <a name="csimplemap-class"></a>Класс CSimpleMap
Этот класс обеспечивает поддержку для массива простое сопоставление.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>  
class CSimpleMap
```  
  
#### <a name="parameters"></a>Параметры  
 `TKey`  
 Тип ключа элемента.  
  
 `TVal`  
 Тип значения элемента.  
  
 `TEqual`  
 Объект признак, определяющий теста проверки на равенство для элементов типа `T`.  
  
## <a name="members"></a>Члены  
  
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
|[CSimpleMap::Add](#add)|Добавляет ключ и соответствующее значение в массив сопоставлений.|  
|[CSimpleMap::FindKey](#findkey)|Находит указанный ключ.|  
|[CSimpleMap::FindVal](#findval)|Поиск конкретного значения.|  
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
 `CSimpleMap`предоставляет поддержку для любого заданного типа массива простое сопоставление `T`, управление массив неупорядоченных ключевые элементы и их связанные значения.  
  
 Параметр `TEqual` предоставляет средства определения функции проверки на равенство для двух элементов типа `T`. Путем создания класса аналогично [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md), можно изменить поведение проверки равенства для любого заданного массива. Например при работе с массив указателей, его можно использовать для определения равенства как в зависимости от значений, на которые ссылаются указатели. Реализация по умолчанию использует **operator==()**.  
  
 Оба `CSimpleMap` и [CSimpleArray](../../atl/reference/csimplearray-class.md) предоставлены для совместимости с предыдущей ATL освобождает и предоставляются более полный и эффективной реализации коллекции [CAtlArray](../../atl/reference/catlarray-class.md) и [CAtlMap](../../atl/reference/catlmap-class.md).  
  
 В отличие от других коллекций карты в ATL и MFC этот класс реализуется с помощью простого массива, а функция Просмотр ищет требует линейного поиска. `CAtlMap`следует использовать, когда массив содержит большое количество элементов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsimpcoll.h  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#91;](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]  
  
##  <a name="add"></a>CSimpleMap::Add  
 Добавляет ключ и соответствующее значение в массив сопоставлений.  
  
```
BOOL Add(const TKey& key, const TVal& val);
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ.  
  
 *Val*  
 Соответствующее значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если ключ и значение, были успешно добавлен, и FALSE в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Каждая пара ключ-значение добавить сопоставление массива памяти освобождается и повторно, чтобы убедиться, что данные для каждой всегда сохраняются последовательно причины. То есть второй ключевой элемент всегда сразу после первого ключа элемента в памяти и т. д.  
  
##  <a name="_arrayelementtype"></a>CSimpleMap::_ArrayElementType  
 Typedef для типа ключа.  
  
```
typedef TVal _ArrayElementType;
```  
  
##  <a name="_arraykeytype"></a>CSimpleMap::_ArrayKeyType  
 Typedef для типа значения.  
  
```
typedef TKey _ArrayKeyType;
```  
  
##  <a name="csimplemap"></a>CSimpleMap::CSimpleMap  
 Конструктор.  
  
```
CSimpleMap();
```  
  
### <a name="remarks"></a>Примечания  
 Инициализирует элементы данных.  
  
##  <a name="dtor"></a>CSimpleMap:: ~ CSimpleMap  
 Деструктор  
  
```
~CSimpleMap();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="findkey"></a>CSimpleMap::FindKey  
 Находит указанный ключ.  
  
```
int FindKey(const TKey& key) const;
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ, который нужно найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает индекс ключа, если объект найден, в противном случае возвращает значение -1.  
  
##  <a name="findval"></a>CSimpleMap::FindVal  
 Поиск конкретного значения.  
  
```
int FindVal(const TVal& val) const;
```  
  
### <a name="parameters"></a>Параметры  
 *Val*  
 Значение, по которому выполняется поиск.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает индекс значения, если он найден, в противном случае возвращает значение -1.  
  
##  <a name="getkeyat"></a>CSimpleMap::GetKeyAt  
 Получает ключ по указанному индексу.  
  
```
TKey& GetKeyAt(int nIndex) const;
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс возвращаемого ключевого поля.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ключ, который ссылается `nIndex`.  
  
### <a name="remarks"></a>Примечания  
 Индекс, переданный `nIndex` должен быть допустимым для возвращаемого значения будут иметь значения.  
  
##  <a name="getsize"></a>CSimpleMap::GetSize  
 Возвращает число записей в массиве сопоставления.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество записей (ключ и значение представляет одну запись) в массиве сопоставления.  
  
##  <a name="getvalueat"></a>CSimpleMap::GetValueAt  
 Получает значение по указанному индексу.  
  
```
TVal& GetValueAt(int nIndex) const;
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс возвращаемого значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение, на который указывает `nIndex`.  
  
### <a name="remarks"></a>Примечания  
 Индекс, переданный `nIndex` должен быть допустимым для возвращаемого значения будут иметь значения.  
  
##  <a name="lookup"></a>CSimpleMap::Lookup  
 Возвращает значение, связанное с указанным ключом.  
  
```
TVal Lookup(const TKey& key) const;
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает соответствующее значение. Если такой ключ не найден, значение NULL возвращается.  
  
##  <a name="remove"></a>CSimpleMap::Remove  
 Удаляет ключ и соответствующее значение.  
  
```
BOOL Remove(const TKey& key);
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если ключа и соответствующего значения были успешно удален, и FALSE в противном случае.  
  
##  <a name="removeall"></a>CSimpleMap::RemoveAll  
 Удаляет все ключи и значения.  
  
```
void RemoveAll();
```  
  
### <a name="remarks"></a>Примечания  
 Удаляет все ключи и значения из массива объекта сопоставления.  
  
##  <a name="removeat"></a>CSimpleMap::RemoveAt  
 Удаляет ключ и соответствующее значение по указанному индексу.  
  
```
BOOL RemoveAt(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс ключа и связанного значения для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE в случае успеха, FALSE, если индекс указан недопустимый индекс.  
  
##  <a name="reverselookup"></a>CSimpleMap::ReverseLookup  
 Возвращает ключ, связанный с заданным значением.  
  
```
TKey ReverseLookup(const TVal& val) const;
```  
  
### <a name="parameters"></a>Параметры  
 *Val*  
 Значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает связанный ключ. Если такой ключ не найден, значение NULL возвращается.  
  
##  <a name="setat"></a>CSimpleMap::SetAt  
 Задает значение, связанное с указанным ключом.  
  
```
BOOL SetAt(const TKey& key, const TVal& val);
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ.  
  
 *Val*  
 Чтобы назначить новое значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если ключ найден и значение было успешно изменена, и FALSE в противном случае.  
  
##  <a name="setatindex"></a>CSimpleMap::SetAtIndex  
 Задает ключ и значение по указанному индексу.  
  
```
BOOL SetAtIndex(  
    int nIndex,
    const TKey& key,
    const TVal& val);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс, ссылаясь на ключ и значение связывания для изменения.  
  
 `key`  
 Новый ключ.  
  
 *Val*  
 Новое значение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает TRUE, если успешно, значение FALSE, если индекс является недопустимым.  
  
### <a name="remarks"></a>Примечания  
 Обновляет ключ и значение, на который указывает `nIndex`.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

