---
title: "CDBPropSet::AddProperty | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBPropSet::AddProperty"
  - "CDBPropSet.AddProperty"
  - "AddProperty"
  - "ATL::CDBPropSet::AddProperty"
  - "ATL.CDBPropSet.AddProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddProperty - метод"
ms.assetid: dc9539d3-1ee4-40f3-9281-2068e6d65e93
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CDBPropSet::AddProperty
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Добавляет свойство в набор свойств.  
  
## Синтаксис  
  
```  
  
      bool AddProperty(   
   DWORD dwPropertyID,   
   const VARIANT& var,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCSTR szValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCWSTR szValue,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   bool bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   BYTE bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   short nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   long nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   float fltValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   double dblValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   CY cyValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
```  
  
#### Параметры  
 *dwPropertyID*  
 \[in\] идентификатор свойства, который требуется добавить.  Используется для инициализации **dwPropertyID** структуры `DBPROP` добавляется в набор свойств.  
  
 `var`  
 \[in\] версия a, используемый для инициализации значения свойства для структуры `DBPROP` добавляется в набор свойств.  
  
 `szValue`  
 \[in\] строка a, используемая для инициализации значения свойства для структуры `DBPROP` добавила в набор свойств.  
  
 `bValue`  
 \[in\] a **byte** или логическое значение, используемые для инициализации значения свойства для структуры `DBPROP` добавляет в набор свойств.  
  
 `nValue`  
 \[in\] целочисленное значение, используемое для инициализации значения свойства для структуры `DBPROP` добавляет в набор свойств.  
  
 *fltValue*  
 \[in\] с плавающей запятой a, используемая для инициализации значения свойства для структуры `DBPROP` добавила в набор свойств.  
  
 `dblValue`  
 \[in\] a с плавающей запятой двойной точности, используемая для инициализации значения свойства для структуры `DBPROP` добавила в набор свойств.  
  
 `cyValue`  
 \[in\] значение валюты CY a, используемый для инициализации значения свойства для структуры `DBPROP` добавляет в набор свойств.  
  
## Возвращаемое значение  
 **true**, если свойство было успешно добавлен.  В противном случае — значение **false**.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDBPropSet](../Topic/CDBPropSet%20Class.md)   
 [DBPROP Structure](https://msdn.microsoft.com/en-us/library/ms717970.aspx)