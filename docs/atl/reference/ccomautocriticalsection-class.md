---
title: "CComAutoCriticalSection Class | Microsoft Docs"
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
  - "ATL.CComAutoCriticalSection"
  - "ATL::CComAutoCriticalSection"
  - "CComAutoCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAutoCriticalSection class"
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComAutoCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComAutoCriticalSection` предоставляет методы для получения объекта и освобождение владение критической секции.  
  
## Синтаксис  
  
```  
  
class CComAutoCriticalSection : public CComCriticalSection  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComAutoCriticalSection::CComAutoCriticalSection](../Topic/CComAutoCriticalSection::CComAutoCriticalSection.md)|Конструктор.|  
|[CComAutoCriticalSection::~CComAutoCriticalSection](../Topic/CComAutoCriticalSection::~CComAutoCriticalSection.md)|Деструктор.|  
  
## Заметки  
 `CComAutoCriticalSection` аналогично для категоризации [CComCriticalSection](../Topic/CComCriticalSection%20Class.md), за исключением того, что `CComAutoCriticalSection` автоматически инициализирует объект критической секции в конструкторе.  
  
 Обычно используется `CComAutoCriticalSection` до имя [AutoCriticalSection](../Topic/CComMultiThreadModel::AutoCriticalSection.md)`typedef`.  Ссылки данного имени `CComAutoCriticalSection` при [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) используется.  
  
 Методы `Init` и `Term` из [CComCriticalSection](../Topic/CComCriticalSection%20Class.md) недоступны при использовании этого класса.  
  
## Иерархия наследования  
 [CComCriticalSection](../Topic/CComCriticalSection%20Class.md)  
  
 `CComAutoCriticalSection`  
  
## Требования  
 **Header:**  atlcore.h  
  
## См. также  
 [CComFakeCriticalSection Class](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComCriticalSection Class](../Topic/CComCriticalSection%20Class.md)