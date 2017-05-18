---
title: "Класс CRBMultiMap | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: a72ddfbf4944f0de5e979f7046872d594017b9cf
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="crbmultimap-class"></a>Класс CRBMultiMap
Этот класс представляет структуру сопоставления, которая позволяет каждый раздел может быть сопоставлен более одного значения, с помощью двоичного дерева красно-черного.  
  
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
 Код, используемый для копирования или перемещения ключа элементов. В разделе [CElementTraits класса](../../atl/reference/celementtraits-class.md) для получения дополнительных сведений.  
  
 `VTraits`  
 Код, используемый для копирования или перемещения элементов значение.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRBMultiMap::CRBMultiMap](#crbmultimap)|Конструктор.|  
|[CRBMultiMap:: ~ CRBMultiMap](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRBMultiMap::FindFirstWithKey](#findfirstwithkey)|Вызовите этот метод, чтобы определить позицию первого элемента с помощью данного ключа.|  
|[CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey)|Этот метод возвращает значение, связанное с помощью данного ключа и обновите значение позиции.|  
|[CRBMultiMap::GetNextWithKey](#getnextwithkey)|Этот метод вызывается для получения элемента, связанного с помощью данного ключа и обновите значение позиции.|  
|[CRBMultiMap::Insert](#insert)|Этот метод используется для вставки пары элементов в схеме.|  
|[CRBMultiMap::RemoveKey](#removekey)|Этот метод используется для удаления всех элементов ключ значение для заданного ключа.|  
  
## <a name="remarks"></a>Примечания  
 `CRBMultiMap`обеспечивает поддержку для любого заданного типа, управление упорядоченный массив ключей элементов и значений массива сопоставления. В отличие от [CRBMap](../../atl/reference/crbmap-class.md) класс, каждый ключ может быть связан с более одного значения.  
  
 Элементов (состоящие из ключа и значения) хранятся в двоичном дереве структуры с помощью [CRBMultiMap::Insert](#insert) метод. Элементы можно удалить с помощью [CRBMultiMap::RemoveKey](#removekey) метод, который удаляет все элементы, которые соответствуют указанным значением ключа.  
  
 Обход дерева стало возможным с методами таких как [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), и [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue). Доступ к потенциально несколько значений каждого ключа является можно с помощью [CRBMultiMap::FindFirstWithKey](#findfirstwithkey), [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), и [CRBMultiMap::GetNextWithKey](#getnextwithkey) методы. В примере показано [CRBMultiMap::CRBMultiMap](#crbmultimap) иллюстрация это на практике.  
  
 `KTraits` И `VTraits` параметры являются признаками классы, содержащие любой дополнительный код, необходимые для копирования или перемещения элементов.  
  
 `CRBMultiMap`является производным от [CRBTree](../../atl/reference/crbtree-class.md), который реализует двоичного дерева с помощью алгоритма красно-черного. Альтернатива `CRBMultiMap` и `CRBMap` предлагаемых [CAtlMap](../../atl/reference/catlmap-class.md) класса. Если только небольшое число элементов должно быть сохранено, рассмотрите возможность использования [CSimpleMap](../../atl/reference/csimplemap-class.md) вместо этого класс.  
  
 Подробное рассмотрение различных классов коллекций и их функции и характеристики производительности в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMultiMap`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="crbmultimap"></a>CRBMultiMap::CRBMultiMap  
 Конструктор.  
  
```
explicit CRBMultiMap(size_t nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nBlockSize`  
 Размер блока.  
  
### <a name="remarks"></a>Примечания  
 `nBlockSize` Параметр измеряется объем памяти, выделяемый при новый элемент является обязательным. Размер блока Уменьшите количество вызовов процедур выделения памяти, но использует больше ресурсов. Значение по умолчанию будет выделить пространство для 10 элементов одновременно.  
  
 См. в документации базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#85;](../../atl/codesnippet/cpp/crbmultimap-class_1.cpp)]  
  
##  <a name="dtor"></a>CRBMultiMap:: ~ CRBMultiMap  
 Деструктор  
  
```
~CRBMultiMap() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все ресурсы, выделенные.  
  
 См. в документации базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
##  <a name="findfirstwithkey"></a>CRBMultiMap::FindFirstWithKey  
 Вызовите этот метод, чтобы определить позицию первого элемента с помощью данного ключа.  
  
```
POSITION FindFirstWithKey(KINARGTYPE key) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Задает ключ, который определяет элемент, который требуется найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ПОЗИЦИЮ первого элемента ключ значение, если ключ найден, значение NULL в противном случае.  
  
### <a name="remarks"></a>Примечания  
 Ключ в `CRBMultiMap` может иметь один или несколько связанных значений. Этот метод будет предоставить значение позиции первого значения (например на самом деле, единственное значение), связанное с этим ключом определенного. Возвращаемое значение позиции может затем использоваться с [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey) или [CRBMultiMap::GetNextWithKey](#getnextwithkey) для получения значения и обновить позицию.  
  
 См. в документации базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
### <a name="example"></a>Пример  
 В примере показано [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="getnextvaluewithkey"></a>CRBMultiMap::GetNextValueWithKey  
 Этот метод возвращает значение, связанное с помощью данного ключа и обновите значение позиции.  
  
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
 Значение позиции, полученные с помощью вызова к [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) или [CRBMultiMap::GetNextWithKey](#getnextwithkey), или предыдущего вызова `GetNextValueWithKey`.  
  
 `key`  
 Задает ключ, который определяет элемент, который требуется найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает пары элементов, связанных с указанным ключом.  
  
### <a name="remarks"></a>Примечания  
 Значение позиции обновляется и указывает следующее значение, связанное с ключом. Если других значений не существует, значение позиции задано значение NULL.  
  
 См. в документации базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
### <a name="example"></a>Пример  
 В примере показано [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="getnextwithkey"></a>CRBMultiMap::GetNextWithKey  
 Этот метод вызывается для получения элемента, связанного с помощью данного ключа и обновите значение позиции.  
  
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
 Значение позиции, полученные с помощью вызова к [CRBMultiMap::FindFirstWithKey](#findfirstwithkey) или [CRBMultiMap::GetNextValueWithKey](#getnextvaluewithkey), или предыдущего вызова `GetNextWithKey`.  
  
 `key`  
 Задает ключ, который определяет элемент, который требуется найти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает следующий [CRBTree::CPair класса](crbtree-class.md#cpair_class) элемент, связанный с указанным ключом.  
  
### <a name="remarks"></a>Примечания  
 Значение позиции обновляется и указывает следующее значение, связанное с ключом. Если других значений не существует, значение позиции задано значение NULL.  
  
 См. в документации базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
##  <a name="insert"></a>CRBMultiMap::Insert  
 Этот метод используется для вставки пары элементов в схеме.  
  
```
POSITION Insert(KINARGTYPE key, VINARGTYPE value) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Значение ключа, чтобы добавить `CRBMultiMap` объекта.  
  
 *value*  
 Значение для добавления `CRBMultiMap` объекта, связанного с `key`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает позицию первого элемента пары ключ значение в `CRBMultiMap` объекта.  
  
### <a name="remarks"></a>Примечания  
 См. в документации базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
### <a name="example"></a>Пример  
 В примере показано [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
##  <a name="removekey"></a>CRBMultiMap::RemoveKey  
 Этот метод используется для удаления всех элементов ключ значение для заданного ключа.  
  
```
size_t RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Задает ключ, определяющий удаляемых элементов.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает число значений, связанных с указанным ключом.  
  
### <a name="remarks"></a>Примечания  
 `RemoveKey`Удаляет все элементы ключ/значение с ключом, который соответствует `key`.  
  
 См. в документации базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
### <a name="example"></a>Пример  
 В примере показано [CRBMultiMap::CRBMultiMap](#crbmultimap).  
  
## <a name="see-also"></a>См. также  
 [Класс CRBTree](../../atl/reference/crbtree-class.md)   
 [Класс CAtlMap](../../atl/reference/catlmap-class.md)   
 [Класс CRBMap](../../atl/reference/crbmap-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

