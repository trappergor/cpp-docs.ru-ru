---
title: "Макросы для шаблонов поставщика OLE DB | Microsoft Docs"
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
  - "vc.templates.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "макросы, Шаблоны поставщика OLE DB"
  - "макросы шаблонов поставщика OLE DB"
  - "шаблоны поставщика OLE DB, макросы"
  - "макросы шаблонов поставщика (OLE DB)"
ms.assetid: 909482c5-64ab-4e52-84a9-1c07091db183
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Макросы для шаблонов поставщика OLE DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Макросы поставщика OLE DB предоставляют функции из следующих категорий:  
  
### Макросы сопоставления набора свойств  
  
|||  
|-|-|  
|[BEGIN\_PROPERTY\_SET](../../data/oledb/begin-property-set.md)|Обозначает начало набора свойств.|  
|[BEGIN\_PROPERTY\_SET\_EX](../../data/oledb/begin-property-set-ex.md)|Обозначает начало набора свойств.|  
|[BEGIN\_PROPSET\_MAP](../Topic/BEGIN_PROPSET_MAP.md)|Обозначает начало набора свойств, можно скрывать или указать вне области поставщика.|  
|[CHAIN\_PROPERTY\_SET](../Topic/CHAIN_PROPERTY_SET.md)|Группы свойств цепочек вместе.|  
|[END\_PROPERTY\_SET](../../data/oledb/end-property-set.md)|Отмечает конец набора свойств.|  
|[END\_PROPSET\_MAP](../../data/oledb/end-propset-map.md)|Отмечает конец сопоставления набора свойств.|  
|[PROPERTY\_INFORMATION\_ENTRY](../../data/oledb/property-info-entry.md)|Задает определенное свойство в наборе свойств значение по умолчанию.|  
|[PROPERTY\_INFORMATION\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md)|Задает определенное свойство в наборе свойств значение поставленному вас.  Также можно установить флажки и параметры.|  
|[PROPERTY\_INFORMATION\_ENTRY\_VALUE](../../data/oledb/property-info-entry-value.md)|Задает определенное свойство в наборе свойств значение поставленному вас.|  
  
### Макросы сопоставления столбцов  
  
|||  
|-|-|  
|[BEGIN\_PROVIDER\_COLUMN\_MAP](../../data/oledb/begin-provider-column-map.md)|Обозначает начало записей сопоставления столбцов поставщика.|  
|[END\_PROVIDER\_COLUMN\_MAP](../../data/oledb/end-provider-column-map.md)|Отмечает конец записей сопоставления столбцов поставщика.|  
|[PROVIDER\_COLUMN\_ENTRY](../../data/oledb/provider-column-entry.md)|Представляет определенный столбец поддерживается поставщиком.|  
|[PROVIDER\_COLUMN\_ENTRY\_GN](../../data/oledb/provider-column-entry-gn.md)|Представляет определенный столбец поддерживается поставщиком.  Можно указать размер, тип данных, точность, масштаб и набор строк схемы GUID столбца.|  
|[PROVIDER\_COLUMN\_ENTRY\_FIXED](../Topic/PROVIDER_COLUMN_ENTRY_FIXED.md)|Представляет определенный столбец поддерживается поставщиком.  Можно задать тип данных столбца.|  
|[PROVIDER\_COLUMN\_ENTRY\_LENGTH](../../data/oledb/provider-column-entry-length.md)|Представляет определенный столбец поддерживается поставщиком.  Можно указать размер столбца.|  
|[PROVIDER\_COLUMN\_ENTRY\_STR](../../data/oledb/provider-column-entry-str.md)|Представляет определенный столбец поддерживается поставщиком.  Это предполагает, что тип столбца строки.|  
|[PROVIDER\_COLUMN\_ENTRY\_TYPE\_LENGTH](../../data/oledb/provider-column-entry-type-length.md)|Представляет определенный столбец поддерживается поставщиком.  Как PROVIDER\_COLUMN\_ENTRY\_LENGTH, но также указать тип данных, а также размер столбца.|  
|[PROVIDER\_COLUMN\_ENTRY\_WSTR](../../data/oledb/provider-column-entry-wstr.md)|Представляет определенный столбец поддерживается поставщиком.  Это предполагает, что тип столбца характерная черта символов юникода.|  
  
### Макросы набора строк схемы  
  
|||  
|-|-|  
|[BEGIN\_SCHEMA\_MAP](../../data/oledb/begin-schema-map.md)|Обозначает начало сопоставления схемы.|  
|[SCHEMA\_ENTRY](../../data/oledb/schema-entry.md)|Связывает GUID с классом.|  
|[END\_SCHEMA\_MAP](../../data/oledb/end-schema-map.md)|Отмечает конец сопоставления схемы.|  
  
## См. также  
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)   
 [Ссылка на шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-reference.md)