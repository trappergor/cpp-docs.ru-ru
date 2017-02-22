---
title: "CAtlMap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlMap"
  - "CAtlMap"
  - "ATL::CAtlMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlMap class"
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CAtlMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для создания и управления объекта сопоставления.  
  
## Синтаксис  
  
```  
  
      template<  
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >  
>  
class CAtlMap  
```  
  
#### Параметры  
 `K`  
 Тип ключевого положения.  
  
 V  
 Тип значения.  
  
 `KTraits`  
 Код, используемый для копирования или перемещения ключевые элементы.  Дополнительные сведения см. в разделе [класс CElementTraits](../../atl/reference/celementtraits-class.md).  
  
 `VTraits`  
 Код, используемый для копирования или перемещения элементов значения.  
  
## Члены  
  
### Открытые определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlMap::KINARGTYPE](../Topic/CAtlMap::KINARGTYPE.md)|Тип используемого, когда ключ будет передан в качестве входного аргумента|  
|[CAtlMap::KOUTARGTYPE](../Topic/CAtlMap::KOUTARGTYPE.md)|Тип используемого, когда ключ будет возвращен как выходной аргумент.|  
|[CAtlMap::VINARGTYPE](../Topic/CAtlMap::VINARGTYPE.md)|Тип используемого, когда будет передано значение в качестве входного аргумента.|  
|[CAtlMap::VOUTARGTYPE](../Topic/CAtlMap::VOUTARGTYPE.md)|Тип используемого при получении передается значение в качестве аргумента вывода.|  
  
### Общие классы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlMap::CPair Class](../Topic/CAtlMap::CPair%20Class.md)|Класс, содержащий элементы ключа и значения.|  
  
### Элементы данных CPair  
  
|Имя|Описание|  
|---------|--------------|  
|[CPair::m\_key](../Topic/CAtlMap::CPair::m_key.md)|Элемент данных хранения является ключевым элементом.|  
|[CPair::m\_value](../Topic/CAtlMap::CPair::m_value.md)|Элемент данных хранения элемент значения.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlMap::CAtlMap](../Topic/CAtlMap::CAtlMap.md)|Конструктор.|  
|[CAtlMap::~CAtlMap](../Topic/CAtlMap::~CAtlMap.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlMap::AssertValid](../Topic/CAtlMap::AssertValid.md)|Вызовите этот метод, чтобы вызвать ASSERT, если `CAtlMap` недопустимо.|  
|[CAtlMap::DisableAutoRehash](../Topic/CAtlMap::DisableAutoRehash.md)|Вызывайте этот метод для отключения автоматического повторного хэширования объекта `CAtlMap`.|  
|[CAtlMap::EnableAutoRehash](../Topic/CAtlMap::EnableAutoRehash.md)|Этот метод вызывается для включения автоматического повторного хэширования объекта `CAtlMap`.|  
|[CAtlMap::GetAt](../Topic/CAtlMap::GetAt.md)|Вызовите этот метод, чтобы вернуть элемент в указанной позиции в сопоставлении.|  
|[CAtlMap::GetCount](../Topic/CAtlMap::GetCount.md)|Вызовите этот метод, чтобы получить количество элементов в сопоставлении.|  
|[CAtlMap::GetHashTableSize](../Topic/CAtlMap::GetHashTableSize.md)|Вызовите этот метод, чтобы указать количество позиций в хэш\-таблице сопоставления.|  
|[CAtlMap::GetKeyAt](../Topic/CAtlMap::GetKeyAt.md)|Вызовите этот метод, чтобы извлечь ключ, хранящийся в заданной позиции в объекте `CAtlMap`.|  
|[CAtlMap::GetNext](../Topic/CAtlMap::GetNext.md)|Этот метод вызывается для получения указателя на следующие сопоставления элемента, хранящегося в объекте `CAtlMap`.|  
|[CAtlMap::GetNextAssoc](../Topic/CAtlMap::GetNextAssoc.md)|Возвращает следующий элемент для итерации.|  
|[CAtlMap::GetNextKey](../Topic/CAtlMap::GetNextKey.md)|Вызовите этот метод, чтобы получить следующий ключ из объекта `CAtlMap`.|  
|[CAtlMap::GetNextValue](../Topic/CAtlMap::GetNextValue.md)|Вызовите этот метод, чтобы получить следующее значение из объекта `CAtlMap`.|  
|[CAtlMap::GetStartPosition](../Topic/CAtlMap::GetStartPosition.md)|Вызовите этот метод, чтобы начать итерацию сопоставления.|  
|[CAtlMap::GetValueAt](../Topic/CAtlMap::GetValueAt.md)|Вызовите этот метод, чтобы извлечь значение, сохраненное в заданной позиции в объекте `CAtlMap`.|  
|[CAtlMap::InitHashTable](../Topic/CAtlMap::InitHashTable.md)|Этот метод вызывается для инициализации хэш\-таблицы.|  
|[CAtlMap::IsEmpty](../Topic/CAtlMap::IsEmpty.md)|Вызывайте этот метод для проверки на наличие объекта пустого сопоставления.|  
|[CAtlMap::Lookup](../Topic/CAtlMap::Lookup.md)|Вызовите этот метод, чтобы найти ключи и значения в объекте `CAtlMap`.|  
|[CAtlMap::Rehash](../Topic/CAtlMap::Rehash.md)|Этот метод вызывается в перефразированию объектом `CAtlMap`.|  
|[CAtlMap::RemoveAll](../Topic/CAtlMap::RemoveAll.md)|Вызовите этот метод, чтобы удалить все элементы из объекта `CAtlMap`.|  
|[CAtlMap::RemoveAtPos](../Topic/CAtlMap::RemoveAtPos.md)|Вызовите этот метод, чтобы удалить элемент на заданной позиции в объекте `CAtlMap`.|  
|[CAtlMap::RemoveKey](../Topic/CAtlMap::RemoveKey.md)|Вызовите этот метод, чтобы удалить элемент из объекта `CAtlMap` заданный ключ.|  
|[CAtlMap::SetAt](../Topic/CAtlMap::SetAt.md)|Вызовите этот метод, чтобы вставить пару элемента в сопоставление.|  
|[CAtlMap::SetOptimalLoad](../Topic/CAtlMap::SetOptimalLoad.md)|Вызовите этот метод, чтобы задать оптимальную загрузку объекта `CAtlMap`.|  
|[CAtlMap::SetValueAt](../Topic/CAtlMap::SetValueAt.md)|Вызовите этот метод, чтобы изменить значение, хранящееся в заданной позиции в объекте `CAtlMap`.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CAtlMap::operator](../Topic/CAtlMap::operator.md)|Заменяет или добавить новый элемент в `CAtlMap`.|  
  
## Заметки  
 `CAtlMap` обеспечивает поддержку массивов любого заданного типа, сопоставления для управления неупорядоченными массив ключевых положений и связанных с ними значений.  Элементы \(состоящ из ключа и значения\) хранятся используя алгоритм хэширования, при включении больших объемов эффективно для хранения и восстановимых данных.  
  
 Параметры `KTraits` и признаков `VTraits` классы, содержащие любой дополнительный код необходимо копировать или перемещать элементы.  
  
 Альтернативой `CAtlMap` предложена классом [CRBMap](../../atl/reference/crbmap-class.md).  `CRBMap` ключ магазинов также ключ\-значение, но отображаются другие характеристики производительности.  Время, затраченное для вставки элемента, поиска или удаления ключа из объекта `CRBMap` порядка  *log\(n\)*, где *n* \- количество элементов.  Для `CAtlMap`, все эти операции обычно занимают постоянное время, хотя наихудшие варианты развития событий могут оказаться *n*.  Поэтому в обычном случае `CAtlMap` быстрее.  
  
 Других различий между `CRBMap` и `CAtlMap` будет ясным повторяя через сохраненные элементы.  В `CRBMap` элементы посещены в порядке сортировки.  В `CAtlMap` элементы не упорядочиваются, и порядок может быть выведен.  
  
 Если несколько элементов должны храниться рекомендуется использовать класс [CSimpleMap](../../atl/reference/csimplemap-class.md).  
  
 Дополнительные сведения см. в разделе [Классы коллекций библиотеку ATL](../../atl/atl-collection-classes.md).  
  
## Требования  
 **Header:** atlcoll.h  
  
## См. также  
 [Образец бегущей строки](../../top/visual-cpp-samples.md)   
 [Образец UpdatePV](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)