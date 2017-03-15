---
title: "PROVIDER_COLUMN_ENTRY_STR | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROVIDER_COLUMN_ENTRY_STR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROVIDER_COLUMN_ENTRY_STR - макрос"
ms.assetid: f1c27dd6-9ab8-4821-8685-d4dd15e76e88
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# PROVIDER_COLUMN_ENTRY_STR
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет определенный столбец поддерживается поставщиком.  
  
## Синтаксис  
  
```  
  
PROVIDER_COLUMN_ENTRY_STR(  
name  
, ordinal, member )  
```  
  
#### Параметры  
 *name*  
 \[in\] имя столбца.  
  
 `ordinal`  
 \[in\] число столбцов.  Если столбец не будет столбца закладки, номер столбца не должно быть равно 0.  
  
 `member`  
 \[in\] переменную\-член в классе данных, который хранит данные.  
  
## Заметки  
 Этот макрос, когда предполагается, что будет данные столбца [DBTYPE\_STR](https://msdn.microsoft.com/en-us/library/ms711251.aspx).  
  
## Пример  
 В разделе [BEGIN\_PROVIDER\_COLUMN\_MAP](../../data/oledb/begin-provider-column-map.md).  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)