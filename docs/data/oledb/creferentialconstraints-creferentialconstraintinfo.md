---
title: "CReferentialConstraints, CReferentialConstraintInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "m_szUniqueName"
  - "m_szCatalog"
  - "DELETE_RULE"
  - "m_szUniqueCatalog"
  - "CONSTRAINT_NAME"
  - "CReferentialConstraintInfo"
  - "MATCH_OPTION"
  - "m_szSchema"
  - "m_szDeleteRule"
  - "m_szUpdateRule"
  - "m_szUniqueSchema"
  - "CReferentialConstraints"
  - "m_szName"
  - "CONSTRAINT_CATALOG"
  - "m_szMatchOption"
  - "CONSTRAINT_SCHEMA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CONSTRAINT_CATALOG"
  - "CONSTRAINT_NAME"
  - "CONSTRAINT_SCHEMA"
  - "CReferentialConstraintInfo - класс параметров"
  - "CReferentialConstraints typedef - класс"
  - "DELETE_RULE"
  - "DESCRIPTION - данные-член класса"
  - "m_szCatalog"
  - "m_szDeleteRule"
  - "m_szDescription"
  - "m_szMatchOption"
  - "m_szName"
  - "m_szSchema"
  - "m_szUniqueCatalog"
  - "m_szUniqueName"
  - "m_szUniqueSchema"
  - "m_szUpdateRule"
  - "MATCH_OPTION"
ms.assetid: 5d485358-be29-41c2-b0ce-19e023598e73
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# CReferentialConstraints, CReferentialConstraintInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызовите **CReferentialConstraints** класс typedef для реализации его класс **CReferentialConstraintInfo** параметра.  
  
## Заметки  
 Дополнительные сведения см. в разделе [Классы набора строк схемы и классах typedef](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md) при использовании классов typedef.  
  
 Этот класс определяет справочные ограничения, определенные в каталоге, принадлежащих заданных пользователем.  
  
 В следующей таблице перечислены элементы данных класса и соответствующие столбцы OLE DB.  В разделе [Набор строк REFERENTIAL\_CONSTRAINTS](https://msdn.microsoft.com/en-us/library/ms719737.aspx) справочника *программиста OLE DB* дополнительные сведения о схеме и столбцам.  
  
|Элементы данных|Столбцы OLE DB|  
|---------------------|--------------------|  
|m\_szCatalog|CONSTRAINT\_CATALOG|  
|m\_szSchema|CONSTRAINT\_SCHEMA|  
|m\_szName|CONSTRAINT\_NAME|  
|m\_szUniqueCatalog|UNIQUE\_CONSTRAINT\_CATALOG|  
|m\_szUniqueSchema|UNIQUE\_CONSTRAINT\_SCHEMA|  
|m\_szUniqueName|UNIQUE\_CONSTRAINT\_NAME|  
|m\_szMatchOption|MATCH\_OPTION|  
|m\_szUpdateRule|UPDATE\_RULE|  
|m\_szDeleteRule|DELETE\_RULE|  
|m\_szDescription|DESCRIPTION|  
  
## Требования  
 **Header:**  atldbsch.h  
  
## См. также  
 [Класс CRestrictions](../Topic/CRestrictions%20Class.md)