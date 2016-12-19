---
title: "CRBMap Class | Microsoft Docs"
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
  - "ATL.CRBMap"
  - "CRBMap"
  - "ATL::CRBMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRBMap class"
ms.assetid: 658e94dc-e835-4356-aed1-1513e1f66969
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRBMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс представляет структуру сопоставления с помощью Красн\- Черное бинарный дерево.  
  
## Синтаксис  
  
```  
  
      template<   
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >   
> class CRBMap : public CRBTree< K, V, KTraits, VTraits >  
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
|[CRBMap::CRBMap](../Topic/CRBMap::CRBMap.md)|Конструктор.|  
|[CRBMap::~CRBMap](../Topic/CRBMap::~CRBMap.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRBMap::Lookup](../Topic/CRBMap::Lookup.md)|Вызовите этот метод, чтобы найти ключи и значения в объекте `CRBMap`.|  
|[CRBMap::RemoveKey](../Topic/CRBMap::RemoveKey.md)|Вызовите этот метод, чтобы удалить элемент из объекта `CRBMap` заданный ключ.|  
|[CRBMap::SetAt](../Topic/CRBMap::SetAt.md)|Вызовите этот метод, чтобы вставить пару элемента в сопоставление.|  
  
## Заметки  
 `CRBMap` обеспечивает поддержку массивов сопоставления любого заданного типа, управление упорядоченный массив ключевых положений и связанных с ними значений.  Каждый ключ может иметь только одно связанное значение.  Элементы \(состоящ из ключа и значения\) хранятся в структуре дерева бинарный дерева, используя метод [CRBMap::SetAt](../Topic/CRBMap::SetAt.md).  Элементы могут быть удалены с помощью метода [CRBMap::RemoveKey](../Topic/CRBMap::RemoveKey.md), который удаляет элемент со значением заданного ключа.  
  
 Обход дерева становится возможным с методами, как [CRBTree::GetHeadPosition](../Topic/CRBTree::GetHeadPosition.md), [CRBTree::GetNext](../Topic/CRBTree::GetNext.md) и [CRBTree::GetNextValue](../Topic/CRBTree::GetNextValue.md).  
  
 Параметры `KTraits` и признаков `VTraits` классы, содержащие любой дополнительный код необходимо копировать или перемещать элементы.  
  
 `CRBMap` является производным от [CRBTree](../../atl/reference/crbtree-class.md), который реализует бинарный дерево с помощью Красн\- Черный алгоритм.  [CRBMultiMap](../../atl/reference/crbmultimap-class.md) изменение, разрешить несколько значений для каждого ключа.  Она слишком является производным от `CRBTree`, и поэтому акций множество функций с `CRBMap`.  
  
 Альтернативой обоим `CRBMap` и `CRBMultiMap` предложена классом [CAtlMap](../../atl/reference/catlmap-class.md).  Когда небольшое количество элементов должны храниться рекомендуется использовать класс [CSimpleMap](../../atl/reference/csimplemap-class.md).  
  
 Для более полного обсуждения различных классов коллекций и их функции и характеристик производительности см. в разделе [Классы коллекций библиотеку ATL](../../atl/atl-collection-classes.md).  
  
## Иерархия наследования  
 [CRBTree](../../atl/reference/crbtree-class.md)  
  
 `CRBMap`  
  
## Требования  
 **Header:** atlcoll.h  
  
## См. также  
 [CRBTree Class](../../atl/reference/crbtree-class.md)   
 [CAtlMap Class](../../atl/reference/catlmap-class.md)   
 [CRBMultiMap Class](../../atl/reference/crbmultimap-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)