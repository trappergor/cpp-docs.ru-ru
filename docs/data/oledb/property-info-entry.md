---
title: "PROPERTY_INFO_ENTRY | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROPERTY_INFO_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROPERTY_INFO_ENTRY - макрос"
ms.assetid: f7bd23d6-52b4-4d6a-aa9a-1fca9834c8dc
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# PROPERTY_INFO_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет конкретное свойство в наборе свойств.  
  
## Синтаксис  
  
```  
  
PROPERTY_INFO_ENTRY(  
dwPropID   
)  
  
```  
  
#### Параметры  
 *dwPropID*  
 \[входные данные\] Значение [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx), которое может использоваться вместе с GUID набора свойств для идентификации свойства.  
  
## Заметки  
 Этот макрос задает в качестве значения свойства типа `DWORD` значение по умолчанию, определенное в ATLDB.H. Чтобы задать свойству нужное вам значение, используйте [PROPERTY\_INFO\_ENTRY\_VALUE](../../data/oledb/property-info-entry-value.md). Чтобы задать одновременно [VARTYPE](http://msdn.microsoft.com/ru-ru/317b911b-1805-402d-a9cb-159546bc88b4) и [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) для свойства, используйте [PROPERTY\_INFO\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md).  
  
## Пример  
 См. раздел [BEGIN\_PROPSET\_MAP](../Topic/BEGIN_PROPSET_MAP.md).  
  
## Требования  
 **Заголовок:** atldb.h  
  
## См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)