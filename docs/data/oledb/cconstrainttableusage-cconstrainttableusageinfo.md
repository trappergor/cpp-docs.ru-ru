---
title: "CConstraintTableUsage, CConstraintTableUsageInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CConstraintTableUsageInfo"
  - "CONSTRAINT_TABLE_USAGE"
  - "m_szTableSchema"
  - "m_szConstraintCatalog"
  - "CONSTRAINT_NAME"
  - "m_szTableCatalog"
  - "m_szConstraintSchema"
  - "m_szTableName"
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_SCHEMA"
  - "CConstraintTableUsage"
  - "m_szConstraintName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CConstraintTableUsage typedef - класс"
  - "CConstraintTableUsageInfo - класс параметров"
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_NAME"
  - "CONSTRAINT_SCHEMA"
  - "CONSTRAINT_TABLE_USAGE"
  - "m_szConstraintCatalog"
  - "m_szConstraintName"
  - "m_szConstraintSchema"
  - "m_szTableCatalog"
  - "m_szTableName"
  - "m_szTableSchema"
  - "TABLE_CATALOG"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: 666b44de-3922-4c5e-ad17-d5ea27120174
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CConstraintTableUsage, CConstraintTableUsageInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызовите **CConstraintTableUsage** класс typedef для реализации его класс **CConstraintTableUsageInfo** параметра.  
  
## Заметки  
 Дополнительные сведения см. в разделе [Классы набора строк схемы и классах typedef](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md) при использовании классов typedef.  
  
 Этот класс определяет таблицы, используемые справочными ограничениями, ограничения уникальности, проверочными ограничениями и проверочными утверждениями, определенные в каталоге и, принадлежащих определенному пользователю.  
  
 В следующей таблице перечислены элементы данных класса и соответствующие столбцы OLE DB.  В разделе [Набор строк CONSTRAINT\_TABLE\_USAGE](https://msdn.microsoft.com/en-us/library/ms724522.aspx) справочника *программиста OLE DB* дополнительные сведения о схеме и столбцам.  
  
|Элементы данных|Столбцы OLE DB|  
|---------------------|--------------------|  
|m\_szTableCatalog|TABLE\_CATALOG|  
|m\_szTableSchema|TABLE\_SCHEMA|  
|m\_szTableName|TABLE\_NAME|  
|m\_szConstraintCatalog|CONSTRAINT\_CATALOG|  
|m\_szConstraintSchema|CONSTRAINT\_SCHEMA|  
|m\_szConstraintName|CONSTRAINT\_NAME|  
  
## Требования  
 **Header:**  atldbsch.h  
  
## См. также  
 [Класс CRestrictions](../Topic/CRestrictions%20Class.md)