---
title: "OLE DB Consumer Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attributes [C++], database"
  - "attributes [C++], data access"
  - "databases [C++], attributes"
  - "OLE DB consumers [C++], attributes"
  - "database attributes [C++]"
  - "attributes [C++], OLE DB consumer"
ms.assetid: 017b591f-8f9a-42b4-84d5-cc42a21ab0cc
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# OLE DB Consumer Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Атрибуты объекта\-получателя OLE DB впрыскивают код на основании [Шаблоны объекта\-получателя OLE DB](../data/oledb/ole-db-consumer-templates-reference.md)создание рабочего объект\-получатель OLE DB, который выполняет такие задачи, как таблицы, выполнение команд и доступ к данным.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|[db\_accessor](../windows/db-accessor.md)|Привязывает столбцы в наборе строк и привязывает их к сопоставлениям соответствующего метода доступа.|  
|[db\_column](../windows/db-column.md)|Привязывает указанный столбец в набор строк.|  
|[db\_command](../windows/db-command.md)|Выполняет команду OLE DB.|  
|[db\_param](../windows/db-param.md)|Связывает указанная переменная члена с входом или параметром вывода.|  
|[db\_source](../windows/db-source.md)|Создает и инкапсулирует соединение с помощью поставщика к источнику данных.|  
|[db\_table](../windows/db-table.md)|Открывает таблицу OLE DB.|  
  
## См. также  
 [Attributes by Group](../windows/attributes-by-group.md)