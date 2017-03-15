---
title: "PROPERTY_INFO_ENTRY_EX | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROPERTY_INFO_ENTRY_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROPERTY_INFO_ENTRY_EX - макрос"
ms.assetid: af32dfcd-4c50-449d-af3b-48d21bd67a04
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# PROPERTY_INFO_ENTRY_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет конкретное свойство в наборе свойств.  
  
## Синтаксис  
  
```  
  
PROPERTY_INFO_ENTRY_EX(  
dwPropID  
,  
vt  
,  
dwFlags  
,  
value  
,  
options  
)  
  
```  
  
#### Параметры  
 *dwPropID*  
 \[входные данные\] Значение [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx), которое может использоваться вместе с GUID набора свойств для идентификации свойства.  
  
 *vt*  
 \[входные данные\] [VARTYPE](http://msdn.microsoft.com/ru-ru/317b911b-1805-402d-a9cb-159546bc88b4) этой записи свойства.  
  
 `dwFlags`  
 \[входные данные\] Значение [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx), описывающее эту запись свойства.  
  
 *значение*  
 \[входные данные\] Значение свойства с типом `DWORD`.  
  
 `options`  
 **DBPROPOPTIONS\_REQUIRED** или **DBPROPOPTIONS\_SETIFCHEAP**. Как правило, поставщику не нужно задавать `options`, так как он задан потребителем.  
  
## Заметки  
 С помощью этого макроса можно напрямую указать значение свойства типа `DWORD`, а также параметры и флаги. Чтобы задать свойству значение по умолчанию, определенное в ATLDB. H, используйте [PROPERTY\_INFO\_ENTRY](../../data/oledb/property-info-entry.md). Чтобы задать свойству значение по своему усмотрению без параметров или флагов, используйте [PROPERTY\_INFO\_ENTRY\_VALUE](../../data/oledb/property-info-entry-value.md).  
  
## Пример  
 См. раздел [BEGIN\_PROPSET\_MAP](../Topic/BEGIN_PROPSET_MAP.md).  
  
## Требования  
 **Заголовок:** atldb.h  
  
## См. также  
 [Макросы для шаблонов поставщика OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Шаблоны поставщика OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Архитектура шаблона поставщика OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Создание поставщика OLE DB](../../data/oledb/creating-an-ole-db-provider.md)