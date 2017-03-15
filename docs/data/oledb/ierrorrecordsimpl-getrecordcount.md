---
title: "IErrorRecordsImpl::GetRecordCount | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IErrorRecordsImpl::GetRecordCount"
  - "ATL::IErrorRecordsImpl::GetRecordCount"
  - "IErrorRecordsImpl.GetRecordCount"
  - "ATL.IErrorRecordsImpl.GetRecordCount"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRecordCount - метод"
ms.assetid: 44388bc3-1c64-4491-a1c5-28f3497ef040
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IErrorRecordsImpl::GetRecordCount
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает число записей в объекте набора записей OLE DB.  
  
## Синтаксис  
  
```  
  
      STDMETHOD( GetRecordCount )(  
   ULONG *pcRecords   
);  
```  
  
#### Параметры  
 В разделе [IErrorRecords::GetRecordCount](https://msdn.microsoft.com/en-us/library/ms722724.aspx) справочника *программиста OLE DB*.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)