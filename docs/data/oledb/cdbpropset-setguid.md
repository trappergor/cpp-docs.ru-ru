---
title: "CDBPropSet::SetGUID | Microsoft Docs"
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
  - "ATL.CDBPropSet.SetGUID"
  - "CDBPropSet.SetGUID"
  - "ATL::CDBPropSet::SetGUID"
  - "SetGUID"
  - "CDBPropSet::SetGUID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddProperty - метод"
  - "SetGUID - метод"
ms.assetid: a4cce036-cf1f-4897-9712-7b01eaf887ff
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBPropSet::SetGUID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает значение поля **guidPropertySet** структуры **DBPROPSET**.  
  
## Синтаксис  
  
```  
  
      void SetGUID(   
   const GUID& guid    
) throw( );  
```  
  
#### Параметры  
 `guid`  
 \[in\] идентификатор GUID, используемый для задания поле **guidPropertySet** структуры [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx).  
  
## Заметки  
 Это поле может быть задано также [конструктор](../Topic/CDBPropSet::CDBPropSet.md).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDBPropSet](../Topic/CDBPropSet%20Class.md)