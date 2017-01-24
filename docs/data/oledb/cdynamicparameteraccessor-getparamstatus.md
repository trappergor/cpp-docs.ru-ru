---
title: "CDynamicParameterAccessor::GetParamStatus | Microsoft Docs"
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
  - "CDynamicParameterAccessor::GetParamStatus"
  - "CDynamicParameterAccessor.GetParamStatus"
  - "ATL.CDynamicParameterAccessor.GetParamStatus"
  - "ATL::CDynamicParameterAccessor::GetParamStatus"
  - "GetParamStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamStatus - метод"
ms.assetid: 9300225a-616c-4a7d-82d0-8c2ecd4d8185
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::GetParamStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Извлекает состояние указанного параметра, хранящиеся в буфере.  
  
## Синтаксис  
  
```  
  
      bool GetParamStatus(  
   DBORDINAL nParam,  
   DBSTATUS* pStatus  
);  
DBSTATUS* GetParamStatus(   
   DBORDINAL nParam    
) const throw( );  
```  
  
#### Параметры  
 `nParam`  
 \[in\] параметр \(начиная с 1\).  Параметр 0 зарезервировано для возвращаемых значений.  Параметр индекс параметра на основании своего порядке в вызове SQL или хранимой процедуры.  Пример см. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md).  
  
 `pStatus`  
 \[out\] указатель на переменную, содержащую состояние `DBSTATUS` указанного параметра.  Сведения о значениях `DBSTATUS` см. в разделе [Состояние](https://msdn.microsoft.com/en-us/library/ms722617.aspx) справочника *программиста OLE* DB или поиск `DBSTATUS` в oledb.h.  
  
## Заметки  
 Первое переопределения возвращается **true** в успехе или **false** при сбое.  Второе переопределение указывает на память, содержащий состояние указанного параметра.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)