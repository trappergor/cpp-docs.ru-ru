---
title: "CDBPropIDSet::CDBPropIDSet | Microsoft Docs"
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
  - "ATL::CDBPropIDSet::CDBPropIDSet"
  - "CDBPropIDSet"
  - "CDBPropIDSet.CDBPropIDSet"
  - "CDBPropIDSet::CDBPropIDSet"
  - "ATL.CDBPropIDSet.CDBPropIDSet"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBPropIDSet - класс, конструктор"
ms.assetid: e68cc20e-fce2-4cc1-9e9d-05c542334cc8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBPropIDSet::CDBPropIDSet
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Конструктор.  Инициализирует **rgProperties**, **cProperties** и \(при необходимости\) поля **guidPropertySet** структуры [DBPROPIDSET](https://msdn.microsoft.com/en-us/library/ms717981.aspx).  
  
## Синтаксис  
  
```  
  
      CDBPropIDSet(  
   const GUID& guid   
);  
CDBPropIDSet(   
   const CDBPropIDSet& propidset    
);  
CDBPropIDSet( );  
```  
  
#### Параметры  
 `guid`  
 \[in\] идентификатор GUID, используемый для инициализации поля **guidPropertySet**.  
  
 *propidset*  
 \[in\] другой объект `CDBPropIDSet` для построения копирования.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDBPropIDSet](../../data/oledb/cdbpropidset-class.md)   
 [CDBPropIDSet::SetGUID](../Topic/CDBPropIDSet::SetGUID.md)