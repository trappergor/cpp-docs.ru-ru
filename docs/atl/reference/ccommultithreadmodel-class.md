---
title: "CComMultiThreadModel Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComMultiThreadModel"
  - "ATL.CComMultiThreadModel"
  - "ATL::CComMultiThreadModel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL - библиотека, многопоточность"
  - "CComMultiThreadModel class"
  - "работа с потоками [ATL]"
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComMultiThreadModel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComMultiThreadModel` поддерживает потокобезопасные методы для увеличения и уменьшения значения переменной.  
  
## Синтаксис  
  
```  
  
class CComMultiThreadModel  
  
```  
  
## Члены  
  
### Открытые определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|[CComMultiThreadModel::AutoCriticalSection](../Topic/CComMultiThreadModel::AutoCriticalSection.md)|Класс [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) ссылок.|  
|[CComMultiThreadModel::CriticalSection](../Topic/CComMultiThreadModel::CriticalSection.md)|Класс [CComCriticalSection](../Topic/CComCriticalSection%20Class.md) ссылок.|  
|[CComMultiThreadModel::ThreadModelNoCS](../Topic/CComMultiThreadModel::ThreadModelNoCS.md)|Класс [CComMultiThreadModelNoCS](../Topic/CComMultiThreadModelNoCS%20Class.md) ссылок.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComMultiThreadModel::Decrement](../Topic/CComMultiThreadModel::Decrement.md)|\(Статический\) Уменьшает значение заданной переменной потокобезопасным способом.|  
|[CComMultiThreadModel::Increment](../Topic/CComMultiThreadModel::Increment.md)|\(Статический\) Увеличивает значение заданной переменной потокобезопасным способом.|  
  
## Заметки  
 Обычно используется `CComMultiThreadModel` через одно из имен `typedef` 2 или [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) или [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md).  Класс, ссылающегося на каждым зависит от `typedef` потоковая модель используется, как показано в следующей таблице:  
  
|typedef|Работа с потоками Единственной|Потоковая модель Подразделение|Свободная работа с потоками|  
|-------------|------------------------------------|------------------------------------|---------------------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S\=`CComSingleThreadModel`; M\=`CComMultiThreadModel`  
  
 `CComMultiThreadModel` само определяет имя `typedef` 3.  `AutoCriticalSection` и `CriticalSection` ссылаются на классы, которые предоставляют методы для получения и освобождение владение критической секции.  Класс [CComMultiThreadModelNoCS](../Topic/CComMultiThreadModelNoCS%20Class.md) ссылок `ThreadModelNoCS`.  
  
## Требования  
 **Header:**  atlbase.h  
  
## См. также  
 [CComSingleThreadModel Class](../../atl/reference/ccomsinglethreadmodel-class.md)   
 [CComAutoCriticalSection Class](../../atl/reference/ccomautocriticalsection-class.md)   
 [CComCriticalSection Class](../Topic/CComCriticalSection%20Class.md)   
 [Class Overview](../../atl/atl-class-overview.md)