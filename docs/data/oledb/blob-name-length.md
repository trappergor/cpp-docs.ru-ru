---
title: "BLOB_NAME_LENGTH | Microsoft Docs"
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
  - "BLOB_NAME_LENGTH"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BLOB_NAME_LENGTH - макрос"
ms.assetid: 38150260-a127-486d-a7ab-0d01b731b6fd
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BLOB_NAME_LENGTH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используется с `BEGIN_COLUMN_MAP` и `END_COLUMN_MAP` для привязки большой двоичный объект \([БОЛЬШОЙ ДВОИЧНЫЙ ОБЪЕКТ](https://msdn.microsoft.com/en-us/library/ms711511.aspx)\).  Аналогично [BLOB\_NAME](../../data/oledb/blob-name.md), за исключением того, что этот макрос также получает длину в байтах столбца данных больших двоичных объектов.  
  
## Синтаксис  
  
```  
  
BLOB_NAME_LENGTH(  
pszName  
,   
IID  
,   
flags  
,   
data  
,   
length )  
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
  
 *length*  
 \[out\]\) \(фактическая длина в байтах столбцов БОЛЬШИХ ДВОИЧНОГО ОБЪЕКТА.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../Topic/Macros%20and%20Global%20Functions%20for%20OLE%20DB%20Consumer%20Templates.md)   
 [BEGIN\_COLUMN\_MAP](../Topic/BEGIN_COLUMN_MAP.md)   
 [END\_COLUMN\_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN\_ENTRY](../../data/oledb/column-entry.md)   
 [BLOB\_NAME](../../data/oledb/blob-name.md)   
 [BLOB\_NAME\_LENGTH\_STATUS](../../data/oledb/blob-name-length-status.md)   
 [BLOB\_NAME\_STATUS](../Topic/BLOB_NAME_STATUS.md)