---
title: "BLOB_NAME | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BLOB_NAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_NAME - макрос"
ms.assetid: 757acd0d-946d-447d-937e-94ecd700ba38
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# BLOB_NAME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используется с `BEGIN_COLUMN_MAP` и `END_COLUMN_MAP` для привязки большой двоичный объект \([БОЛЬШОЙ ДВОИЧНЫЙ ОБЪЕКТ](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\).  Аналогично [BLOB\_ENTRY](../Topic/BLOB_ENTRY.md), за исключением того, что этот макрос имеет имя столбца вместо числа столбцов.  
  
## Синтаксис  
  
```  
  
BLOB_NAME(  
pszName  
,   
IID  
,   
flags  
,   
data )  
```  
  
#### Параметры  
 `pszName`  
 \[in\] указатель на имени столбца.  Имя должно быть строкой юникод.  Можно выполнить путем установки «L» перед именем, например: `L"MyColumn"`.  
  
 *IID*  
 \[in\] интерфейс GUID, например **IDD\_ISequentialStream**, используется для извлечения БОЛЬШОЙ ДВОИЧНЫЙ ОБЪЕКТ.  
  
 `flags`  
 \[in\] флажки Хранилище\- режима заданное OLE составили модель хранения \(например, **STGM\_READ**\).  
  
 `data`  
 \[in\] соответствующий элемент данных в записи пользователя.  
  
## Пример  
 В разделе [Как определить, извлечение БОЛЬШОЙ ДВОИЧНЫЙ ОБЪЕКТ?](../../data/oledb/retrieving-a-blob.md).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_NAME\_LENGTH](../../data/oledb/blob-name-length.md)   
 [BLOB\_NAME\_LENGTH\_STATUS](../../data/oledb/blob-name-length-status.md)   
 [BLOB\_NAME\_STATUS](../Topic/BLOB_NAME_STATUS.md)