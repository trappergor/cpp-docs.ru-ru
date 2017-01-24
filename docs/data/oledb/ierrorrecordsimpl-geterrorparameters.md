---
title: "IErrorRecordsImpl::GetErrorParameters | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IErrorRecordsImpl::GetErrorParameters"
  - "ATL.IErrorRecordsImpl.GetErrorParameters"
  - "IErrorRecordsImpl.GetErrorParameters"
  - "GetErrorParameters"
  - "ATL::IErrorRecordsImpl::GetErrorParameters"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorParameters - метод"
ms.assetid: 9bafac52-399e-4e0e-8365-b9f83074cdd5
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IErrorRecordsImpl::GetErrorParameters
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает параметры ошибки.  
  
## Синтаксис  
  
```  
  
      STDMETHOD( GetErrorParameters )(  
   ULONG ulRecordNum,  
   DISPPARAMS *pdispparams   
);  
```  
  
#### Параметры  
 В разделе [IErrorRecords::GetErrorParameters](https://msdn.microsoft.com/en-us/library/ms715793.aspx) справочника *программиста OLE DB*.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)