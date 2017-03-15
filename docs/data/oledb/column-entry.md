---
title: "COLUMN_ENTRY | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY - макрос"
ms.assetid: a10aef29-6d70-49ec-b572-5b5c4abe1b46
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# COLUMN_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет привязку в наборе строк к конкретному столбцу в наборе строк.  
  
## Синтаксис  
  
```  
  
COLUMN_ENTRY(  
nOrdinal  
,   
data  
 )  
  
```  
  
#### Параметры  
 В разделе [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) справочника *программиста OLE DB*.  
  
 `nOrdinal`  
 \[in\] число столбцов.  
  
 `data`  
 \[in\] соответствующий элемент данных в записи пользователя.  
  
## Заметки  
 Макрос `COLUMN_ENTRY` используется в следующих местах:  
  
-   Между макросами [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md) и [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md).  
  
-   Между макросами [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) и [END\_ACCESSOR](../Topic/END_ACCESSOR.md).  
  
-   Между макросами [BEGIN\_PARAM\_MAP](../Topic/BEGIN_PARAM_MAP.md) и [END\_PARAM\_MAP](../../data/oledb/end-param-map.md).  
  
## Пример  
 Примеры см. в разделах [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md) и [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md), макроса.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md)   
 [COLUMN\_ENTRY\_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN\_ENTRY\_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../Topic/COLUMN_ENTRY_PS_LENGTH_STATUS.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../Topic/COLUMN_ENTRY_PS_STATUS.md)   
 [COLUMN\_ENTRY\_TYPE](../Topic/COLUMN_ENTRY_TYPE.md)   
 [COLUMN\_ENTRY\_TYPE\_SIZE](../Topic/COLUMN_ENTRY_TYPE_SIZE.md)   
 [END\_ACCESSOR](../Topic/END_ACCESSOR.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)