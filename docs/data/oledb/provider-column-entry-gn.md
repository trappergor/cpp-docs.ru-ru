---
title: "PROVIDER_COLUMN_ENTRY_GN | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROVIDER_COLUMN_ENTRY_GN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROVIDER_COLUMN_ENTRY_GN - макрос"
ms.assetid: be77ba85-634c-4e28-832f-d2fa40413254
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# PROVIDER_COLUMN_ENTRY_GN
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет определенный столбец поддерживается поставщиком.  
  
## Синтаксис  
  
```  
  
PROVIDER_COLUMN_ENTRY_GN (  
name  
, ordinal, flags, colSize, dbtype, precision, scale, guid )  
```  
  
#### Параметры  
 *name*  
 \[in\] имя столбца.  
  
 `ordinal`  
 \[in\] число столбцов.  Если столбец не будет столбца закладки, номер столбца не должно быть равно 0.  
  
 `flags`  
 \[in\] указывает, как данные возвращаются.  См. описание `dwFlags` в [Структуры DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 *colSize*  
 \[in\] размер столбца.  
  
 `dbtype`  
 \[in\] указывает тип данных значения.  См. описание **wType** в [Структуры DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 *точность*  
 \[in\] указывает точность для использования при получении данных при *dbType*`DBTYPE_NUMERIC` или **DBTYPE\_DECIMAL**.  См. описание **bPrecision** в [Структуры DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 `scale`  
 \[in\] указывает масштаб для использования при получении данных при dbType `DBTYPE_NUMERIC` или **DBTYPE\_DECIMAL**.  См. описание **bScale** в [Структуры DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 `guid`  
 Набор строк схемы GUID.  В разделе [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) справочника *программиста OLE DB* список наборов строк схемы и их GUID.  
  
## Заметки  
 Позволяет указать размер, тип данных, точность, масштаб и набор строк схемы GUID столбца.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)