---
title: "COLUMN_ENTRY_PS_LENGTH | Microsoft Docs"
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
  - "COLUMN_ENTRY_PS_LENGTH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY_PS_LENGTH - макрос"
ms.assetid: d63ab895-a4df-4183-ac09-cf2311222408
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COLUMN_ENTRY_PS_LENGTH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет привязку в наборе строк к конкретному столбцу в базе данных.  
  
## Синтаксис  
  
```  
  
COLUMN_ENTRY_PS_LENGTH(  
nOrdinal  
,   
nPrecision  
,   
nScale  
,   
data  
,   
length  
 )  
  
```  
  
#### Параметры  
 В разделе [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) справочника *программиста OLE DB*.  
  
 `nOrdinal`  
 \[in\] число столбцов, начиная с одним.  Закладка соответствует столбцу ноль.  
  
 `nPrecision`  
 \[in\] максимальная точность столбца требуется выполнить привязку.  
  
 `nScale`  
 \[in\] масштаба столбца требуется выполнить привязку.  
  
 `data`  
 \[in\] соответствующий элемент данных в записи пользователя.  
  
 *length*  
 \[in\] переменная, привязываемая к длине столбца.  
  
## Заметки  
 Позволяет определить точность и масштаб столбца требуется выполнить привязку.  Этот макрос поддерживает переменную *длину*.  Он используется в следующих местах:  
  
-   Между макросами [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md) и [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md).  
  
-   Между макросами [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) и [END\_ACCESSOR](../Topic/END_ACCESSOR.md).  
  
-   Между макросами [BEGIN\_PARAM\_MAP](../Topic/BEGIN_PARAM_MAP.md) и [END\_PARAM\_MAP](../../data/oledb/end-param-map.md).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN\_ENTRY\_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../Topic/COLUMN_ENTRY_PS_LENGTH_STATUS.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../Topic/COLUMN_ENTRY_PS_STATUS.md)   
 [END\_ACCESSOR](../Topic/END_ACCESSOR.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)