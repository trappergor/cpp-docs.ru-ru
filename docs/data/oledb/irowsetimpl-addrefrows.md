---
title: "IRowsetImpl::AddRefRows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetImpl::AddRefRows"
  - "AddRefRows"
  - "IRowsetImpl.AddRefRows"
  - "ATL::IRowsetImpl::AddRefRows"
  - "ATL.IRowsetImpl.AddRefRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRefRows - метод"
ms.assetid: adc0989b-7592-432e-82d9-df4445431531
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::AddRefRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Добавляет счетчик ссылок в дескриптор существующей строки.  
  
## Синтаксис  
  
```  
  
      STDMETHOD( AddRefRows )(  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[]   
);  
```  
  
#### Параметры  
 В разделе [IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) справочника *программиста OLE DB*.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IRowsetImpl](../Topic/IRowsetImpl%20Class.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)   
 [IRowsetImpl::GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)   
 [IRowsetImpl::ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)