---
title: Класс CRBMultiMap | Документы Microsoft
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
ms.openlocfilehash: 6ec016df268b702fd8b26d742d702ac38b95fa06
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365195"
---
# <a name="crbmultimap-class"></a>Класс CRBMultiMap
Этот класс представляет структуру сопоставления, которая позволяет каждый ключ может быть сопоставлен более одного значения, с помощью двоичного дерева красный-черный.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename K,
         typename V, 
         class KTraits = CElementTraits<K>, 
         class VTraits = CElementTraits<V>>  
class CRBMultiMap : public CRBTree<K, V, KTraits, VTraits>
```    
  
#### <a name="parameters"></a>Параметры  
 `K`  
 Тип ключа элемента.  
  
 *V*  
 Тип значения элемента.  
  
 `KTraits`  
 Код, используемый для копирования или перемещения элементов ключа. В разделе [CElementTraits класса](../../atl/reference/celementtraits-class.md) для получения дополнительных сведений.  
  
 `VTraits`  
 Код, используемый для копирования или перемещения элементов значение.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|Конструктор.|  
|[CRBMultiMap:: ~ CRBMultiMap](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)|Вызовите этот метод, чтобы определить позицию первого элемента с указанным ключом.|  
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|Этот метод вызывается для получения значения, связанного с данным ключом и обновите значение позиции.|  
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|Этот метод вызывается для получения элемента, связанного с данным ключом и обновите значение позиции.|  
|[CRBMultiMap::Insert](#insert)|Этот метод служит для вставки пары элементов в сопоставление.|  
|[CRBMultiMap::RemoveKey](#removekey)|Этот метод используется для удаления всех элементов ключ значение для указанного ключа.|  
  
## <a name="remarks"></a>Примечания  
 `CRBMultiMap` предоставляет поддержку для массива сопоставление любого конкретного типа управления упорядоченный массив ключей элементов и значений. В отличие от [CRBMap](../../atl/reference/crbmap-class.md) класс, каждый ключ может быть сопоставлен более одного значения.  
  
 Элементы (состоящей из ключа и значения) хранятся в двоичное дерево структуры с помощью [CRBMultiMap::Insert](#insert) метод. Элементы можно удалить с помощью [CRBMultiMap::RemoveKey](#removekey) метод, который удаляет все элементы, которые соответствуют указанным ключом.  
  
 Обход дерева стало возможным с помощью методов например [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), и [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue). Доступ к потенциально несколько значений ключа для каждого возможного использует [CRBMultiMap::FindFirstWithKey](#findfirstwithkey), [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), и [CRBMultiMap::GetNextWithKey ](#getnextwithkey) методы. Далее приведен пример [CRBMultiMap::CRBMultiMap](#crbmultimap) иллюстрация это на практике.  
  
 `KTraits` И `VTraits` являются классов признаки, которые содержат любой дополнительный код, необходимые для копирования или перемещения элементов.  
  
 `CRBMultiMap` является производным от [CRBTree](../../atl/reference/crbtree-class.md), который реализует двоичного дерева с помощью алгоритма красный-черный. Это альтернатива `CRBMultiMap` и `CRBMap` предлагаемых [CAtlMap](../../atl/reference/catlmap-class.md) класса. Когда небольшое количество элементов должно быть сохранено, рассмотрите возможность использования [CSimpleMap](../../atl/reference/csimplemap-class.md) вместо этого класс.  
  
 Более полное описание различных классов коллекций и их возможности и характеристики производительности см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
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
 `nBlockSize`  
 Размер блока.  
  
### <a name="remarks"></a>Примечания  
 `nBlockSize` Параметр — это мера объем памяти, выделяемый при новый элемент является обязательным. Увеличенный размер блока, уменьшите количество вызовов процедур выделения памяти, но использует больше ресурсов. Значение по умолчанию будет выделить место для 10 элементов одновременно.  
  
 См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#85](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]  
  
##  <a name="dtor"></a>  CRBMultiMap:: ~ CRBMultiMap  
 Деструктор  
  
```
~CRBMultiMap() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все ресурсы, выделенные.  
  
 См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
##  <a name="findfirstwithkey"></a>  CRBMultiMap::FindFirstWithKey  
 Вызовите этот метод, чтобы определить позицию первого элемента с указанным ключом.  
  
```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Задает ключ, определяющий элемента, который требуется найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ПОЗИЦИЮ первого элемента ключ значение, если ключ найден, значение NULL в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Ключ в `CRBMultiMap` может иметь один или несколько связанных значений. Этот метод предоставит значение позиции первое значение (которое может оказаться единственным значением), связанные с определенной разделу. Возвращаемое значение позиции затем могут использоваться с [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey) или [CRBMultiMap::GetNextWithKey](#getnextwithkey) для получения значения и обновления позицию.  
  
 См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="getnextvaluewithkey"></a>  CRBMultiMap::GetNextValueWithKey  
 Этот метод вызывается для получения значения, связанного с данным ключом и обновите значение позиции.  
  
```
const V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
V& GetNextValueWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Значение позиции, полученные с помощью вызова для [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) или [CRBMultiMap::GetNextWithKey](#getnextwithkey), или предыдущим вызовом `GetNextValueWithKey`.  
  
 `key`  
 Задает ключ, определяющий элемента, который требуется найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает пары элементов, связанных с указанным ключом.  
  
### <a name="remarks"></a>Примечания  
 Значение позиции обновляется и указывает на следующее значение, связанное с ключом. Если других значений не существует, значение позиции будет равно NULL.  
  
 См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="getnextwithkey"></a>  CRBMultiMap::GetNextWithKey  
 Этот метод вызывается для получения элемента, связанного с данным ключом и обновите значение позиции.  
  
```
const CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) const throw();
CPair* GetNextWithKey(
    POSITION& pos,
    KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Значение позиции, полученные с помощью вызова для [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) или [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), или предыдущим вызовом `GetNextWithKey`.  
  
 `key`  
 Задает ключ, определяющий элемента, который требуется найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает следующий [CRBTree::CPair класса](crbtree-class.md#cpair_class) элемента, связанного с данным ключом.  
  
### <a name="remarks"></a>Примечания  
 Значение позиции обновляется и указывает на следующее значение, связанное с ключом. Если других значений не существует, значение позиции будет равно NULL.  
  
 См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
##  <a name="insert"></a>  CRBMultiMap::Insert  
 Этот метод служит для вставки пары элементов в сопоставление.  
  
```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Чтобы добавить значение ключа `CRBMultiMap` объекта.  
  
 *значение*  
 Значения для добавления в `CRBMultiMap` объекта, связанного с `key`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает позицию пары ключ значение элемента в `CRBMultiMap` объекта.  
  
### <a name="remarks"></a>Примечания  
 См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="removekey"></a>  CRBMultiMap::RemoveKey  
 Этот метод используется для удаления всех элементов ключ значение для указанного ключа.  
  
```
size_t RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Задает ключ, определяющий элементы для удаления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает количество значений, связанных с указанным ключом.  
  
### <a name="remarks"></a>Примечания  
 `RemoveKey` Удаляет все элементы ключ значение с ключом, который соответствует `key`.  
  
 См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
### <a name="example"></a>Пример  
 Далее приведен пример [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
## <a name="see-also"></a>См. также  
 [Класс CRBTree](../../atl/reference/crbtree-class.md)   
 [Класс CAtlMap](../../atl/reference/catlmap-class.md)   
 [Класс CRBMap](../../atl/reference/crbmap-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
