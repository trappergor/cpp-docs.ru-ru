---
title: "CDynamicParameterAccessor::SetParamStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicParameterAccessor::SetParamStatus"
  - "ATL.CDynamicParameterAccessor.SetParamStatus"
  - "ATL::CDynamicParameterAccessor::SetParamStatus"
  - "CDynamicParameterAccessor.SetParamStatus"
  - "SetParamStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetParamStatus - метод"
ms.assetid: 0c2271f6-457d-46ca-88b7-4590aadb20d7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicParameterAccessor::SetParamStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает состояние указанного параметра, хранящиеся в буфере.  
  
## Синтаксис  
  
```  
  
      bool SetParamStatus(  
   DBORDINAL nParam,  
   DBSTATUS status  
);  
```  
  
#### Параметры  
 `nParam`  
 \[in\] параметр \(начиная с 1\).  Параметр 0 зарезервировано для возвращаемых значений.  Параметр индекс параметра на основании своего порядке в вызове SQL или хранимой процедуры.  Пример см. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md).  
  
 *status*  
 \[in\] состояние `DBSTATUS` указанного параметра.  Сведения о значениях `DBSTATUS` см. в разделе [Состояние](https://msdn.microsoft.com/en-us/library/ms722617.aspx) справочника *программиста OLE* DB или поиск `DBSTATUS` в oledb.h.  
  
## Заметки  
 Возвращает **true** в успехе или **false** при сбое.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)