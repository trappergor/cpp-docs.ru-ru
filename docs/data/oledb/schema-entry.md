---
title: "SCHEMA_ENTRY | Microsoft Docs"
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
  - "SCHEMA_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SCHEMA_ENTRY - макрос"
ms.assetid: e8bee479-80f3-417e-8f41-cdaddd49690c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SCHEMA_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Связывает GUID с классом.  
  
## Синтаксис  
  
```  
  
      SCHEMA_ENTRY(  
   guid,  
   rowsetClass   
);   
```  
  
#### Параметры  
 `guid`  
 Набор строк схемы GUID.  В разделе [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) справочника *программиста OLE DB* список наборов строк схемы и их GUID.  
  
 *rowsetClass*  
 Класс, который будет создан для представления набора строк схемы.  
  
## Заметки  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) можно затем запрос сопоставление для списка GUID, он может создать набор строк, если ему присваивается идентификатор GUID.  Набор строк схемы `IDBSchemaRowsetImpl` создает аналогичен стандартному `CRowsetImpl`\- производного класса, за исключением того, что он должен предоставить метод **Выполнить**, который имеет следующую сигнатуру:  
  
 `HRESULT Execute (LONG* pcRowsAffected, ULONG cRestrictions,`  
  
 `const VARIANT* rgRestrictions)`  
  
 Эта функция **Выполнить** заполняет данные набора строк.  Мастер проекта библиотеки ATL создает, как описано в разделе [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) в *справочнике программиста OLE DB*, 3 начальных наборов строк схемы в проекте для каждой из 3 необходимых схем OLE DB:  
  
-   `DBSCHEMA_TABLES`  
  
-   **DBSCHEMA\_COLUMNS**  
  
-   **DBSCHEMA\_PROVIDER\_TYPES**  
  
 Мастер также добавляет 3 соответствующей записи в сопоставлении схемы.  Дополнительные сведения см. в разделе [Создание шаблона поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md) об использовании мастера для создания поставщика.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [BEGIN\_SCHEMA\_MAP](../../data/oledb/begin-schema-map.md)   
 [END\_SCHEMA\_MAP](../../data/oledb/end-schema-map.md)