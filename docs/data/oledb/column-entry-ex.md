---
title: "COLUMN_ENTRY_EX | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "COLUMN_ENTRY_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COLUMN_ENTRY_EX - макрос"
ms.assetid: dfad1b67-51c3-4289-b89a-da42d7e8bb88
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# COLUMN_ENTRY_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет привязку в наборе строк к конкретному столбцу в базе данных.  
  
## Синтаксис  
  
```  
  
COLUMN_ENTRY_EX(  
nOrdinal  
,   
wType  
,   
nLength  
,   
nPrecision  
,   
nScale  
,   
data  
,   
length  
,   
status  
 )  
  
```  
  
#### Параметры  
 В разделе [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) справочника *программиста OLE DB*.  
  
 `nOrdinal`  
 \[in\] число столбцов.  
  
 `wType`  
 \[in\] тип данных.  
  
 `nLength`  
 \[in\] размер данных в байтах.  
  
 `nPrecision`  
 \[in\] максимальная точность для использования при получении данных и `wType``DBTYPE_NUMERIC`.  В противном случае этот параметр игнорируется.  
  
 `nScale`  
 \[in\] масштаб для использования при получении данных и `wType``DBTYPE_NUMERIC` или **DBTYPE\_DECIMAL**.  
  
 `data`  
 \[in\] соответствующий элемент данных в записи пользователя.  
  
 *length*  
 \[in\] переменная, привязываемая к длине столбца.  
  
 *status*  
 \[in\] переменная, привязываемая к состояние столбца.  
  
## Заметки  
 Макрос `COLUMN_ENTRY_EX` используется в следующих местах:  
  
-   Между макросами [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md) и [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md).  
  
-   Между макросами [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md) и [END\_ACCESSOR](../Topic/END_ACCESSOR.md).  
  
-   Между макросами [BEGIN\_PARAM\_MAP](../Topic/BEGIN_PARAM_MAP.md) и [END\_PARAM\_MAP](../../data/oledb/end-param-map.md).  
  
## Пример  
 В разделе [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN\_ACCESSOR\_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN\_ENTRY\_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN\_ENTRY\_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN\_ENTRY\_LENGTH\_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN\_ENTRY\_PS\_LENGTH\_STATUS](../Topic/COLUMN_ENTRY_PS_LENGTH_STATUS.md)   
 [COLUMN\_ENTRY\_STATUS](../../data/oledb/column-entry-status.md)   
 [COLUMN\_ENTRY\_PS\_STATUS](../Topic/COLUMN_ENTRY_PS_STATUS.md)   
 [END\_ACCESSOR](../Topic/END_ACCESSOR.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)