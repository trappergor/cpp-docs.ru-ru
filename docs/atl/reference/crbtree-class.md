---
title: "CRBTree Class | Microsoft Docs"
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
  - "ATL.CRBTree"
  - "CRBTree"
  - "ATL::CRBTree"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRBTree class"
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRBTree Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для создания и использования Красн\- Черное дерево.  
  
## Синтаксис  
  
```  
  
      template<  
   typename K,  
   typename V,  
   class KTraits = CElementTraits< K >,  
   class VTraits = CElementTraits< V >  
> class CRBTree  
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
  
### Открытые определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|[CRBTree::KINARGTYPE](../Topic/CRBTree::KINARGTYPE.md)|Введите используемый, когда ключ передается в качестве входного аргумента.|  
|[CRBTree::KOUTARGTYPE](../Topic/CRBTree::KOUTARGTYPE.md)|Тип используемого, когда ключ будет возвращен как выходной аргумент.|  
|[CRBTree::VINARGTYPE](../Topic/CRBTree::VINARGTYPE.md)|Тип используемого, когда будет передано значение в качестве входного аргумента.|  
|[CRBTree::VOUTARGTYPE](../Topic/CRBTree::VOUTARGTYPE.md)|Тип используемого при получении передается значение в качестве аргумента вывода.|  
  
### Общие классы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRBTree::CPair Class](../Topic/CRBTree::CPair%20Class.md)|Класс, содержащий элементы ключа и значения.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRBTree::~CRBTree](../Topic/CRBTree::~CRBTree.md)|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CRBTree::FindFirstKeyAfter](../Topic/CRBTree::FindFirstKeyAfter.md)|Вызовите этот метод, чтобы найти положение элемента, который использует следующий ключ доступен.|  
|[CRBTree::GetAt](../Topic/CRBTree::GetAt.md)|Вызовите этот метод, чтобы получить элемент в заданной позиции в дереве.|  
|[CRBTree::GetCount](../Topic/CRBTree::GetCount.md)|Вызовите этот метод, чтобы получить количество элементов в дереве.|  
|[CRBTree::GetHeadPosition](../Topic/CRBTree::GetHeadPosition.md)|Вызовите этот метод, чтобы получить значение положения элемента в начало дерева.|  
|[CRBTree::GetKeyAt](../Topic/CRBTree::GetKeyAt.md)|Вызовите этот метод, чтобы получить ключ из заданной позиции в дереве.|  
|[CRBTree::GetNext](../Topic/CRBTree::GetNext.md)|Вызовите этот метод, чтобы получить указатель к элементу, хранящиеся в объекте `CRBTree` и выдвиньте положение к следующему элементу.|  
|[CRBTree::GetNextAssoc](../Topic/CRBTree::GetNextAssoc.md)|Вызовите этот метод, чтобы получить ключ и значение элемента, хранящегося в сопоставлении и переместить положение к следующему элементу.|  
|[CRBTree::GetNextKey](../Topic/CRBTree::GetNextKey.md)|Вызовите этот метод, чтобы получить ключ элемента, хранящегося в дереве и переместить положение к следующему элементу.|  
|[CRBTree::GetNextValue](../Topic/CRBTree::GetNextValue.md)|Вызовите этот метод, чтобы получить значение элемента, хранящегося в дереве и переместить положение к следующему элементу.|  
|[CRBTree::GetPrev](../Topic/CRBTree::GetPrev.md)|Вызовите этот метод, чтобы получить указатель к элементу, хранящиеся в объекте `CRBTree`, а затем обновите позиция к предыдущему элементу.|  
|[CRBTree::GetTailPosition](../Topic/CRBTree::GetTailPosition.md)|Вызовите этот метод, чтобы получить значение позиции элемента на кабеле дерева.|  
|[CRBTree::GetValueAt](../Topic/CRBTree::GetValueAt.md)|Вызовите этот метод, чтобы извлечь значение, сохраненное в заданной позиции в объекте `CRBTree`.|  
|[CRBTree::IsEmpty](../Topic/CRBTree::IsEmpty.md)|Этот метод вызывается для тестирования для пустого объекта дерева.|  
|[CRBTree::RemoveAll](../Topic/CRBTree::RemoveAll.md)|Вызовите этот метод, чтобы удалить все элементы из объекта **CRBTree** .|  
|[CRBTree::RemoveAt](../Topic/CRBTree::RemoveAt.md)|Вызовите этот метод, чтобы удалить элемент на заданной позиции в объекте **CRBTree** .|  
|[CRBTree::SetValueAt](../Topic/CRBTree::SetValueAt.md)|Вызовите этот метод, чтобы изменить значение, хранящееся в заданной позиции в объекте `CRBTree`.|  
  
## Заметки  
 Красн\- Черное дерево дерево бинарный поиска, которое использует дополнительную квант сведения в узел, чтобы удостовериться, что он остается "сбалансированным", то есть высота дерева не растет несоразмерно большим и не влияет на производительность.  
  
 Этот класс предназначен для использования [CRBMap](../../atl/reference/crbmap-class.md) шаблона и [CRBMultiMap](../../atl/reference/crbmultimap-class.md).  Большая часть методов, составляющие эти производные классы предоставляется `CRBTree`.  
  
 Для более полного обсуждения различных классов коллекций и их функции и характеристик производительности см. в разделе [Классы коллекций библиотеку ATL](../../atl/atl-collection-classes.md).  
  
## Требования  
 **Header:** atlcoll.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)