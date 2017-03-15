---
title: "Класс CXMLAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CXMLAccessor"
  - "CXMLAccessor"
  - "ATL.CXMLAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CXMLAccessor - класс"
ms.assetid: c88c082c-ec2f-4351-8947-a330b15e448a
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Класс CXMLAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Позволяет доступа к источникам данных в виде строковых данных, когда неизвестна схема хранилища данных \(базовая структура\).  
  
## Синтаксис  
  
```  
class CXMLAccessor : public CDynamicStringAccessorW  
```  
  
## Члены  
  
### Методы  
  
|||  
|-|-|  
|[GetXMLColumnData](../Topic/CXMLAccessor::GetXMLColumnData.md)|Извлекает сведения о столбцах.|  
|[GetXMLRowData](../Topic/CXMLAccessor::GetXMLRowData.md)|Извлекает все содержимое таблицы строками.|  
  
## Заметки  
 Однако `CXMLAccessor` отличается от `CDynamicStringAccessorW` поскольку она преобразует все данные, получаемые доступ из хранилища данных, что представляют собой \(помеченные тегами\) данные.  Это особенно полезно для вывода в зависимым к страницам.  Имена тегов XML соответствовали именам столбцов хранилища данных насколько это возможно.  
  
 Используйте методы `CDynamicAccessor` для получения информации о столбцах.  Информация о столбцах используется для динамического создания метода доступа во время выполнения.  
  
 Информация о столбцах хранится в буфере, созданном и управляемым данным классом.  Получение информации о столбцах с помощью [GetXMLColumnData](../Topic/CXMLAccessor::GetXMLColumnData.md) или получить данные столбца строками с помощью [GetXMLRowData](../Topic/CXMLAccessor::GetXMLRowData.md).  
  
## Пример  
 [!code-cpp[NVC_OLEDB_Consumer#14](../../data/oledb/codesnippet/CPP/cxmlaccessor-class_1.cpp)]  
  
## Требования  
 **Заголовок**: atldbcli.h  
  
## См. также  
 [Шаблоны потребителей OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Ссылка на шаблоны потребителя OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [Класс CAccessor](../Topic/CAccessor%20Class.md)   
 [Класс CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md)   
 [Класс CDynamicParameterAccessor](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [Класс CDynamicStringAccessor](../../data/oledb/cdynamicstringaccessor-class.md)   
 [Класс CDynamicStringAccessorA](../../data/oledb/cdynamicstringaccessora-class.md)   
 [Класс CDynamicStringAccessorW](../../data/oledb/cdynamicstringaccessorw-class.md)   
 [Класс CManualAccessor](../Topic/CManualAccessor%20Class.md)