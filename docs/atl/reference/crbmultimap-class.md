---
title: Класс CRBMultiMap | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::CRBMultiMap
- ATLCOLL/ATL::CRBMultiMap::FindFirstWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextValueWithKey
- ATLCOLL/ATL::CRBMultiMap::GetNextWithKey
- ATLCOLL/ATL::CRBMultiMap::Insert
- ATLCOLL/ATL::CRBMultiMap::RemoveKey
dev_langs:
- C++
helpviewer_keywords:
- CRBMultiMap class
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be0b81d1baddfd8d89112f7f7b9d63624a6aa3b6
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43757771"
---
# <a name="crbmultimap-class"></a>Класс CRBMultiMap

Этот класс представляет структуру сопоставления, которая позволяет, что каждый ключ может быть связан более одного значения, с помощью двоичного красно-черного дерева.

## <a name="syntax"></a>Синтаксис

```
template<typename K,
         typename V, 
         class KTraits = CElementTraits<K>, 
         class VTraits = CElementTraits<V>>  
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
```

#### <a name="parameters"></a>Параметры

*K*  
Тип ключа элемента.

*V*  
Тип значения элемента.

*KTraits*  
Код, используемый для копирования или перемещения ключевые элементы. См. в разделе [класс CElementTraits](../../atl/reference/celementtraits-class.md) для получения дополнительных сведений.

*VTraits*  
Код, используемый для копирования или перемещения элементов value.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|Конструктор.|
|[CRBMultiMap:: ~ CRBMultiMap](#dtor)|Деструктор|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)|Вызовите этот метод, чтобы определить позицию первого элемента с данным ключом.|
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|Вызовите этот метод, чтобы получить значение, связанное с данным ключом и обновите значение позиции.|
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|Вызовите этот метод для получения элемента, связанного с данным ключом и обновите значение позиции.|
|[CRBMultiMap::Insert](#insert)|Этот метод используется для вставки пары элементов в сопоставление.|
|[CRBMultiMap::RemoveKey](#removekey)|Этот метод используется для удаления всех элементов ключ значение для заданного ключа.|

## <a name="remarks"></a>Примечания

`CRBMultiMap` предоставляет поддержку для сопоставления массива заданного типа, управление упорядоченный массив ключевые элементы и значения. В отличие от [CRBMap](../../atl/reference/crbmap-class.md) класс, каждый ключ может быть связан с более чем одним значением.

Элементы, (состоящей из ключа и значения) хранятся в двоичном дереве структуры с помощью [CRBMultiMap::Insert](#insert) метод. Элементы можно удалить с помощью [CRBMultiMap::RemoveKey](#removekey) метод, который удаляет все элементы, которые соответствуют заданному ключу.

Обход дерева стало возможным с методами например [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), и [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue). Доступ к потенциально нескольких значений ключа для каждого возможного использует [CRBMultiMap::FindFirstWithKey](#findfirstwithkey), [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), и [CRBMultiMap::GetNextWithKey ](#getnextwithkey) методы. См. в примере [CRBMultiMap::CRBMultiMap](#crbmultimap) иллюстрация это на практике.

*KTraits* и *VTraits* параметры являются traits-классы, содержащие любой дополнительный код, необходимый для копирования или перемещения элементов.

`CRBMultiMap` является производным от [CRBTree](../../atl/reference/crbtree-class.md), который реализует по двоичному дереву с помощью алгоритма красно-черного. Альтернативой `CRBMultiMap` и `CRBMap` предложенного [CAtlMap](../../atl/reference/catlmap-class.md) класса. Если только небольшое количество элементов должно быть сохранено, рассмотрите возможность использования [CSimpleMap](../../atl/reference/csimplemap-class.md) вместо этого класса.

Более полное описание различных классов коллекций и функций и характеристики производительности, см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CRBTree](../../atl/reference/crbtree-class.md)

`CRBMultiMap`

## <a name="requirements"></a>Требования

**Заголовок:** atlcoll.h

##  <a name="crbmultimap"></a>  CRBMultiMap::CRBMultiMap

Конструктор.

```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```

### <a name="parameters"></a>Параметры

*nBlockSize*  
Размер блока.

### <a name="remarks"></a>Примечания

*NBlockSize* параметр — это мера объем памяти, выделяемый при новый элемент является обязательным. Увеличенный размер блока, уменьшите количество вызовов процедур выделения памяти, но использовать больше ресурсов. Значение по умолчанию будет выделить место для 10 элементов за раз.

См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]

##  <a name="dtor"></a>  CRBMultiMap:: ~ CRBMultiMap

Деструктор

```
~CRBMultiMap() throw();
```

### <a name="remarks"></a>Примечания

Освобождает все выделенные ресурсы.

См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.

##  <a name="findfirstwithkey"></a>  CRBMultiMap::FindFirstWithKey

Вызовите этот метод, чтобы определить позицию первого элемента с данным ключом.

```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>Параметры

*key*  
Задает ключ, определяющий элемента, который требуется найти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает ПОЗИЦИЮ первого элемента ключ/значение, если ключ найден, значение NULL в противном случае.

### <a name="remarks"></a>Примечания

Ключ в `CRBMultiMap` может иметь одно или несколько связанных значений. Этот метод предоставит значение позиции первого значения (это на самом деле, возможно только одно значение), связанное с этой конкретный ключ. Возвращаемое значение затем может использоваться с [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey) или [CRBMultiMap::GetNextWithKey](#getnextwithkey) для получения значения и обновляющий положение.

См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.

### <a name="example"></a>Пример

См. в примере [CRBMultiMap::CRBMultiMap](#crbmultimap).

##  <a name="getnextvaluewithkey"></a>  CRBMultiMap::GetNextValueWithKey

Вызовите этот метод, чтобы получить значение, связанное с данным ключом и обновите значение позиции.

```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*  
Значение позиции, полученные с помощью вызова к [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) или [CRBMultiMap::GetNextWithKey](#getnextwithkey), или предыдущим вызовом `GetNextValueWithKey`.

*key*  
Задает ключ, определяющий элемента, который требуется найти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает пары элементов, связанных с указанным ключом.

### <a name="remarks"></a>Примечания

Значение позиции обновляется и указывает на следующее значение, связанное с ключом. Если других значений не существует, значение позиции присваивается значение NULL.

См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.

### <a name="example"></a>Пример

См. в примере [CRBMultiMap::CRBMultiMap](#crbmultimap).

##  <a name="getnextwithkey"></a>  CRBMultiMap::GetNextWithKey

Вызовите этот метод для получения элемента, связанного с данным ключом и обновите значение позиции.

```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```

### <a name="parameters"></a>Параметры

*торговых терминалов*  
Значение позиции, полученные с помощью вызова к [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) или [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), или предыдущим вызовом `GetNextWithKey`.

*key*  
Задает ключ, определяющий элемента, который требуется найти.

### <a name="return-value"></a>Возвращаемое значение

Возвращает следующий [CRBTree::CPair класс](crbtree-class.md#cpair_class) элемента, связанного с данным ключом.

### <a name="remarks"></a>Примечания

Значение позиции обновляется и указывает на следующее значение, связанное с ключом. Если других значений не существует, значение позиции присваивается значение NULL.

См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.

##  <a name="insert"></a>  CRBMultiMap::Insert

Этот метод используется для вставки пары элементов в сопоставление.

```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```

### <a name="parameters"></a>Параметры

*key*  
Значение ключа, чтобы добавить `CRBMultiMap` объекта.

*значение*  
Значение, которое нужно добавить `CRBMultiMap` объект, связанный с *ключ*.

### <a name="return-value"></a>Возвращаемое значение

Возвращает позицию элемента пары ключ/значение в `CRBMultiMap` объекта.

### <a name="remarks"></a>Примечания

См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.

### <a name="example"></a>Пример

См. в примере [CRBMultiMap::CRBMultiMap](#crbmultimap).

##  <a name="removekey"></a>  CRBMultiMap::RemoveKey

Этот метод используется для удаления всех элементов ключ значение для заданного ключа.

```
size_t RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Параметры

*key*  
Задает ключ, определяющий элементы для удаления.

### <a name="return-value"></a>Возвращаемое значение

Возвращает количество значений, связанных с указанным ключом.

### <a name="remarks"></a>Примечания

`RemoveKey` Удаляет все элементы ключ/значение с ключом, который соответствует *ключ*.

См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.

### <a name="example"></a>Пример

См. в примере [CRBMultiMap::CRBMultiMap](#crbmultimap).

## <a name="see-also"></a>См. также

[Класс CRBTree](../../atl/reference/crbtree-class.md)   
[Класс CAtlMap](../../atl/reference/catlmap-class.md)   
[Класс CRBMap](../../atl/reference/crbmap-class.md)   
[Общие сведения о классе](../../atl/atl-class-overview.md)
