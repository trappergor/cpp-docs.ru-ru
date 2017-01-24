---
title: "CComSingleThreadModel Class | Microsoft Docs"
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
  - "ATL.CComSingleThreadModel"
  - "CComSingleThreadModel"
  - "ATL::CComSingleThreadModel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComSingleThreadModel class"
  - "single-threaded applications"
  - "single-threaded applications, ATL - библиотека"
ms.assetid: e5dc30c7-405a-4ba4-8ae9-51937243fce8
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComSingleThreadModel Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для увеличения и уменьшения значения переменной.  
  
## Синтаксис  
  
```  
  
class CComSingleThreadModel  
  
```  
  
## Члены  
  
### Открытые определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|[CComSingleThreadModel::AutoCriticalSection](../Topic/CComSingleThreadModel::AutoCriticalSection.md)|Класс [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md) ссылок.|  
|[CComSingleThreadModel::CriticalSection](../Topic/CComSingleThreadModel::CriticalSection.md)|Класс `CComFakeCriticalSection` ссылок.|  
|[CComSingleThreadModel::ThreadModelNoCS](../Topic/CComSingleThreadModel::ThreadModelNoCS.md)|Ссылается на `CComSingleThreadModel`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComSingleThreadModel::Decrement](../Topic/CComSingleThreadModel::Decrement.md)|Уменьшает значение заданной переменной.  Данная реализация не является потокобезопасной.|  
|[CComSingleThreadModel::Increment](../Topic/CComSingleThreadModel::Increment.md)|Увеличивает значение указанной переменной.  Данная реализация не является потокобезопасной.|  
  
## Заметки  
 `CComSingleThreadModel` предоставляет методы для увеличения и уменьшения значения переменной.  В отличие от [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) и [CComMultiThreadModelNoCS](../Topic/CComMultiThreadModelNoCS%20Class.md), эти методы не являются потокобезопасными.  
  
 Обычно используется `CComSingleThreadModel` через одно из имен `typedef` 2 или [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) или [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md).  Класс, ссылающегося на каждым зависит от `typedef` потоковая модель используется, как показано в следующей таблице:  
  
|typedef|Единая потоковая модель|Потоковая модель Подразделение|Объем свободной потоковой модели|  
|-------------|-----------------------------|------------------------------------|--------------------------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S\=`CComSingleThreadModel`; M\=`CComMultiThreadModel`  
  
 `CComSingleThreadModel` само определяет имя `typedef` 3.  Ссылки `CComSingleThreadModel``ThreadModelNoCS`.  `AutoCriticalSection` и ссылку `CriticalSection` классифицируют [CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md), которая содержит пустые методы, связанные с получение и освобождение владение критической секции.  
  
## Требования  
 **Header:**  atlbase.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)