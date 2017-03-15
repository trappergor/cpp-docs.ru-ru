---
title: "Класс CDynamicStringAccessorA | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicStringAccessorA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicStringAccessorA - класс"
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Класс CDynamicStringAccessorA
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Позволяет получить доступ к источнику данных, когда неизвестна схема базы данных \(базовая структура\).  
  
## Синтаксис  
  
```  
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;  
```  
  
## Заметки  
 Они оба запрос, выборка поставщика все данные, получаемые доступ из хранилища данных в виде строковых данных, но строковых данных ANSI запросов `CDynamicStringAccessor`.  
  
 `CDynamicStringAccessorA` наследует **GetString** и `SetString` из `CDynamicStringAccessor`.  При использовании этих методов в объекте `CDynamicStringAccessorA`, ***BaseType*char**.  
  
## Требования  
 **Заголовок**: atldbcli.h  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Класс CAccessor](../Topic/CAccessor%20Class.md)   
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [Класс CManualAccessor](../Topic/CManualAccessor%20Class.md)   
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)   
 [Класс CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)