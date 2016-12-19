---
title: "CDynamicParameterAccessor::GetParamType | Microsoft Docs"
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
  - "CDynamicParameterAccessor.GetParamType"
  - "CDynamicParameterAccessor:GetParamType"
  - "CDynamicParameterAccessor::GetParamType"
  - "ATL.CDynamicParameterAccessor.GetParamType"
  - "GetParamType"
  - "ATL::CDynamicParameterAccessor::GetParamType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetParamType - метод"
ms.assetid: d9c46775-c2a6-4100-8b69-99f13c52958b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicParameterAccessor::GetParamType
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает тип данных указанного параметра.  
  
## Синтаксис  
  
```  
  
      bool GetParamType(  
   DBORDINAL nParam,  
   DBTYPE* pType   
) const throw( );  
```  
  
#### Параметры  
 `nParam`  
 \[in\] параметр \(начиная с 1\).  Параметр 0 зарезервировано для возвращаемых значений.  Параметр индекс параметра на основании своего порядке в вызове SQL или хранимой процедуры.  Пример см. в разделе [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md).  
  
 `pType`  
 \[out\] указатель на переменную, содержащую тип данных указанного параметра.  
  
## Возвращаемое значение  
 Возвращает **true** в успехе или **false** при сбое.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)