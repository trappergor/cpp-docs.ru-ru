---
title: "IRowsetImpl::m_rgRowHandles | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetImpl::m_rgRowHandles"
  - "IRowsetImpl.m_rgRowHandles"
  - "m_rgRowHandles"
  - "ATL::IRowsetImpl::m_rgRowHandles"
  - "ATL.IRowsetImpl.m_rgRowHandles"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_rgRowHandles"
ms.assetid: d3c2578f-58c4-4301-bf59-cf101a523a95
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::m_rgRowHandles
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сопоставление дескрипторов строк в данный момент, содержащий поставщиком в ответ на `GetNextRows`.  
  
## Синтаксис  
  
```  
  
MapClass  
 m_rgRowHandles;  
  
```  
  
## Заметки  
 Дескрипторы строк удаляются путем вызова `ReleaseRows`.  В разделе [Общие сведения IRowsetImpl](../Topic/IRowsetImpl%20Class.md) для определения *MapClass*.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IRowsetImpl](../Topic/IRowsetImpl%20Class.md)