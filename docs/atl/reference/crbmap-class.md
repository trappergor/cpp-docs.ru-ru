---
title: "Класс CRBMap | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRBMap
- ATLCOLL/ATL::CRBMap
- ATLCOLL/ATL::CRBMap::CRBMap
- ATLCOLL/ATL::CRBMap::Lookup
- ATLCOLL/ATL::CRBMap::RemoveKey
- ATLCOLL/ATL::CRBMap::SetAt
dev_langs: C++
helpviewer_keywords: CRBMap class
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 127f8b0448d141917193d41d11d5ed95576ff482
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="crbmap-class"></a>Класс CRBMap
Этот класс представляет сопоставление структуры, с помощью двоичного дерева красный-черный.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>> 
class CRBMap : public CRBTree<K, V, KTraits, VTraits>
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
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRBMap::CRBMap](#crbmap)|Конструктор.|  
|[CRBMap:: ~ CRBMap](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CRBMap::Lookup](#lookup)|Вызовите этот метод для поиска разделов или значений в `CRBMap` объекта.|  
|[CRBMap::RemoveKey](#removekey)|Этот метод вызывается для удаления элемента из `CRBMap` объекту, заданному ключу.|  
|[CRBMap::SetAt](#setat)|Этот метод служит для вставки пары элементов в сопоставление.|  
  
## <a name="remarks"></a>Примечания  
 `CRBMap`предоставляет поддержку для любого конкретного типа управления упорядоченный массив ключевые элементы и связанные с ними значения массива сопоставления. Каждый раздел может содержать только один связанного значения. Элементы (состоящей из ключа и значения) хранятся в двоичное дерево структуры с помощью [CRBMap::SetAt](#setat) метод. Элементы можно удалить с помощью [CRBMap::RemoveKey](#removekey) метод, который удаляет элемент с заданным значением ключа.  
  
 Обход дерева стало возможным с помощью методов например [CRBTree::GetHeadPosition](../../atl/reference/crbtree-class.md#getheadposition), [CRBTree::GetNext](../../atl/reference/crbtree-class.md#getnext), и [CRBTree::GetNextValue](../../atl/reference/crbtree-class.md#getnextvalue).  
  
 `KTraits` И `VTraits` являются классов признаки, которые содержат любой дополнительный код, необходимые для копирования или перемещения элементов.  
  
 `CRBMap`является производным от [CRBTree](../../atl/reference/crbtree-class.md), который реализует двоичного дерева с помощью алгоритма красный-черный. [CRBMultiMap](../../atl/reference/crbmultimap-class.md) представляет собой вариант, который допускает несколько значений для каждого ключа. Он слишком является производным от `CRBTree`и поэтому имеет множество функций с `CRBMap`.  
  
 Как альтернатива `CRBMap` и `CRBMultiMap` предлагаемых [CAtlMap](../../atl/reference/catlmap-class.md) класса. Когда небольшое количество элементов должно быть сохранено, рассмотрите возможность использования [CSimpleMap](../../atl/reference/csimplemap-class.md) вместо этого класс.  
  
 Более полное описание различных классов коллекций и их возможности и характеристики производительности см. в разделе [классы коллекций ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMap`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcoll.h  
  
##  <a name="crbmap"></a>CRBMap::CRBMap  
 Конструктор.  
  
```
explicit CRBMap(size_t nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nBlockSize`  
 Размер блока.  
  
### <a name="remarks"></a>Примечания  
 `nBlockSize` Параметр — это мера объем памяти, выделяемый при новый элемент является обязательным. Увеличенный размер блока, уменьшите количество вызовов процедур выделения памяти, но использует больше ресурсов. Значение по умолчанию будет выделить место для 10 элементов одновременно.  
  
 См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#81](../../atl/codesnippet/cpp/crbmap-class_1.cpp)]  
  
##  <a name="dtor"></a>CRBMap:: ~ CRBMap  
 Деструктор  
  
```
~CRBMap() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все ресурсы, выделенные.  
  
 См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
##  <a name="lookup"></a>CRBMap::Lookup  
 Вызовите этот метод для поиска разделов или значений в `CRBMap` объекта.  
  
```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const throw(...);
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Задает ключ, определяющий элемента, который требуется найти.  
  
 *value*  
 Переменная, принимающая значение поиск вверх.  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первой форме метода возвращает значение true, если ключ найден, в противном случае — значение false. Второй и третий формы возвращают указатель на [CPair](crbtree-class.md#cpair_class).  
  
### <a name="remarks"></a>Примечания  
 См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#82](../../atl/codesnippet/cpp/crbmap-class_2.cpp)]  
  
##  <a name="removekey"></a>CRBMap::RemoveKey  
 Этот метод вызывается для удаления элемента из `CRBMap` объекту, заданному ключу.  
  
```
bool RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ, соответствующий пары элементов требуется удалить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если ключ найден и удален, и false в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#83](../../atl/codesnippet/cpp/crbmap-class_3.cpp)]  
  
##  <a name="setat"></a>CRBMap::SetAt  
 Этот метод служит для вставки пары элементов в сопоставление.  
  
```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value) throw(...);
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Чтобы добавить значение ключа `CRBMap` объекта.  
  
 *value*  
 Значение для добавления `CRBMap` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает позицию пары ключ значение элемента в `CRBMap` объекта.  
  
### <a name="remarks"></a>Примечания  
 `SetAt`заменяет существующий элемент, если найден соответствующий ключ. Если ключ не найден, создается новый пара ключ значение.  
  
 См. в документации для базового класса [CRBTree](../../atl/reference/crbtree-class.md) сведения о других методах, доступных.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#84](../../atl/codesnippet/cpp/crbmap-class_4.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс CRBTree](../../atl/reference/crbtree-class.md)   
 [Класс CAtlMap](../../atl/reference/catlmap-class.md)   
 [Класс CRBMultiMap](../../atl/reference/crbmultimap-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
