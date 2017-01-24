---
title: "BLOB_ENTRY_LENGTH_STATUS | Microsoft Docs"
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
  - "BLOB_ENTRY_LENGTH_STATUS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_ENTRY_LENGTH_STATUS - макрос"
ms.assetid: 09da67de-421b-4853-9a26-760e38324502
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BLOB_ENTRY_LENGTH_STATUS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используется с `BEGIN_COLUMN_MAP` и `END_COLUMN_MAP` для привязки большой двоичный объект \([БОЛЬШОЙ ДВОИЧНЫЙ ОБЪЕКТ](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\).  Аналогично [BLOB\_ENTRY](../Topic/BLOB_ENTRY.md), за исключением того, что этот макрос также получает длину и состояние столбца БОЛЬШИХ ДВОИЧНОГО ОБЪЕКТА.  
  
## Синтаксис  
  
```  
  
BLOB_ENTRY_LENGTH_STATUS(  
nOrdinal  
,   
IID  
,   
flags  
,   
data  
, length, status )  
```  
  
#### Параметры  
 `nOrdinal`  
 \[in\] число столбцов.  
  
 *IID*  
 \[in\] интерфейс GUID, например **IDD\_ISequentialStream**, используется для извлечения БОЛЬШОЙ ДВОИЧНЫЙ ОБЪЕКТ.  
  
 `flags`  
 \[in\] флажки Хранилище\- режима заданное OLE составили модель хранения \(например, **STGM\_READ**\).  
  
 `data`  
 \[in\] соответствующий элемент данных в записи пользователя.  
  
 *length*  
 \[out\]\) \(фактическая длина в байтах столбцов БОЛЬШИХ ДВОИЧНОГО ОБЪЕКТА.  
  
 *status*  
 \[out\] состояние столбца данных больших двоичных объектов.  
  
## Пример  
 В разделе [Как определить, извлечение БОЛЬШОЙ ДВОИЧНЫЙ ОБЪЕКТ?](../../data/oledb/retrieving-a-blob.md).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_ENTRY](../Topic/BLOB_ENTRY.md)   
 [BLOB\_ENTRY\_LENGTH](../../data/oledb/blob-entry-length.md)   
 [BLOB\_ENTRY\_STATUS](../Topic/BLOB_ENTRY_STATUS.md)