---
title: "CDynamicParameterAccessor::GetParamName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicParameterAccessor::GetParamName"
  - "ATL.CDynamicParameterAccessor.GetParamName"
  - "GetParamName"
  - "CDynamicParameterAccessor.GetParamName"
  - "ATL::CDynamicParameterAccessor::GetParamName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamName - метод"
ms.assetid: 707c08ed-d3d0-4ce8-b23e-20b07202a3e2
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicParameterAccessor::GetParamName
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает имя указанного параметра.  
  
## Синтаксис  
  
```  
  
      LPOLESTR GetParamName(   
   DBORDINAL nParam    
) const throw( );  
```  
  
#### Параметры  
 `nParam`  
 \[in\] параметр \(начиная с 1\).  Параметр 0 зарезервировано для возвращаемых значений.  Параметр индекс параметра на основании своего порядке в вызове SQL или хранимой процедуры.  Пример см. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md).  
  
## Возвращаемое значение  
 Имя указанного параметра.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)