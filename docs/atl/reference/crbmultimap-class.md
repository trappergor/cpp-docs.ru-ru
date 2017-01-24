---
title: "CRBMultiMap Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRBMultiMap"
  - "ATL.CRBMultiMap"
  - "ATL::CRBMultiMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRBMultiMap class"
ms.assetid: 94d3ec0c-3e30-4ab7-a101-d8da4fb8add3
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRBMultiMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс представляет структуру сопоставления, которая позволяет каждый ключ может быть связан с несколькими значениями, используя Красн\- Черное бинарный дерево.  
  
## Синтаксис  
  
```  
  
      template<  
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >  
> class CRBMultiMap : public CRBTree< K, V, KTraits, VTraits >  
```  
  
#### Параметры  
 `K`  
 Тип ключевого положения.  
  
 *V*  
 Тип значения.  
  
 `KTraits`  
 Код, используемый для копирования или перемещения ключевые элементы.  Дополнительные сведения см. в разделе [класс CElementTraits](../../atl/reference/celementtraits-class.md).  
  
 `VTraits`  
 Код, используемый для копирования или перемещения элементов значения.  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRBMultiMap::CRBMultiMap](../Topic/CRBMultiMap::CRBMultiMap.md)|Конструктор.|  
|[CRBMultiMap::~CRBMultiMap](../Topic/CRBMultiMap::~CRBMultiMap.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRBMultiMap::FindFirstWithKey](../Topic/CRBMultiMap::FindFirstWithKey.md)|Вызовите этот метод, чтобы найти позиция первого элемента с указанным ключом.|  
|[CRBMultiMap::GetNextValueWithKey](../Topic/CRBMultiMap::GetNextValueWithKey.md)|Этот метод вызывается для получения значения, связанного с данным ключом, и обновите значение позиции.|  
|[CRBMultiMap::GetNextWithKey](../Topic/CRBMultiMap::GetNextWithKey.md)|Вызовите этот метод, чтобы получить элемент, связанный с данным ключом, и обновите значение позиции.|  
|[CRBMultiMap::Insert](../Topic/CRBMultiMap::Insert.md)|Вызовите этот метод, чтобы вставить пару элемента в сопоставление.|  
|[CRBMultiMap::RemoveKey](../Topic/CRBMultiMap::RemoveKey.md)|Вызовите этот метод, чтобы удалить все элементы ключ\/значение для заданного ключа.|  
  
## Заметки  
 `CRBMultiMap` обеспечивает поддержку массивов сопоставления любого заданного типа, управление упорядоченный массив ключевых положений и значений.  В отличие от класса [CRBMap](../../atl/reference/crbmap-class.md) каждый ключ может быть связан с несколькими значениями.  
  
 Элементы \(состоящ из ключа и значения\) хранятся в структуре дерева бинарный дерева, используя метод [CRBMultiMap::Insert](../Topic/CRBMultiMap::Insert.md).  Элементы могут быть удалены с помощью метода [CRBMultiMap::RemoveKey](../Topic/CRBMultiMap::RemoveKey.md), который удаляет все элементы, которые соответствуют заданный ключ.  
  
 Обход дерева становится возможным с методами, как [CRBTree::GetHeadPosition](../Topic/CRBTree::GetHeadPosition.md), [CRBTree::GetNext](../Topic/CRBTree::GetNext.md) и [CRBTree::GetNextValue](../Topic/CRBTree::GetNextValue.md).  Доступ к потенциально несколько значений, в котором использование методов [CRBMultiMap::FindFirstWithKey](../Topic/CRBMultiMap::FindFirstWithKey.md) ключ, [CRBMultiMap::GetNextValueWithKey](../Topic/CRBMultiMap::GetNextValueWithKey.md) и [CRBMultiMap::GetNextWithKey](../Topic/CRBMultiMap::GetNextWithKey.md).  См. пример для [CRBMultiMap::CRBMultiMap](../Topic/CRBMultiMap::CRBMultiMap.md) для иллюстрации этого на практике.  
  
 Параметры `KTraits` и признаков `VTraits` классы, содержащие любой дополнительный код необходимо копировать или перемещать элементы.  
  
 `CRBMultiMap` является производным от [CRBTree](../../atl/reference/crbtree-class.md), который реализует бинарный дерево с помощью Красн\- Черный алгоритм.  Альтернативой `CRBMultiMap` и `CRBMap` предложена классом [CAtlMap](../../atl/reference/catlmap-class.md).  Когда небольшое количество элементов должны храниться рекомендуется использовать класс [CSimpleMap](../../atl/reference/csimplemap-class.md).  
  
 Для более полного обсуждения различных классов коллекций и их функции и характеристик производительности см. в разделе [Классы коллекций библиотеку ATL](../../atl/atl-collection-classes.md).  
  
## Иерархия наследования  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMultiMap`  
  
## Требования  
 **Header:** atlcoll.h  
  
## См. также  
 [CRBTree Class](../../atl/reference/crbtree-class.md)   
 [CAtlMap Class](../../atl/reference/catlmap-class.md)   
 [CRBMap Class](../../atl/reference/crbmap-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)