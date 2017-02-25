---
title: "PROPERTY_INFO_ENTRY_VALUE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROPERTY_INFO_ENTRY_VALUE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROPERTY_INFO_ENTRY_VALUE - макрос"
ms.assetid: 9690f7f3-fb20-4a7e-a75f-8a3a1cb1ce0d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# PROPERTY_INFO_ENTRY_VALUE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет конкретное свойство в набор свойств.  
  
## Синтаксис  
  
```  
  
PROPERTY_INFO_ENTRY_VALUE(  
dwPropID  
, value )  
```  
  
#### Параметры  
 *dwPropID*  
 \[in\] a [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) значение, можно использовать совместно с свойством GUID для указания свойства.  
  
 *значение*  
 \[in\] значение свойства типа `DWORD`.  
  
## Заметки  
 С помощью этого макроса можно непосредственно определить значение свойства типа `DWORD`.  Для задания свойства значение по умолчанию, определенное в ATLDB.H, используйте [PROPERTY\_INFORMATION\_ENTRY](../../data/oledb/property-info-entry.md).  Чтобы задать значение, флажки и параметры свойства, использующие [PROPERTY\_INFORMATION\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md).  
  
## Пример  
 В разделе [BEGIN\_PROPSET\_MAP](../Topic/BEGIN_PROPSET_MAP.md).  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)