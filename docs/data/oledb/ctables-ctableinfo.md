---
title: "CTables, CTableInfo | Microsoft Docs"
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
  - "m_szCatalog"
  - "TABLE_SCHEMA"
  - "CTables"
  - "TABLE_NAME"
  - "TABLE_CATALOG"
  - "CTableInfo"
  - "m_guidTable"
  - "m_szType"
  - "m_szSchema"
  - "m_szName"
  - "TABLE_GUID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTableInfo - класс параметров"
  - "CTables typedef - класс"
  - "DESCRIPTION - данные-член класса"
  - "m_guidTable"
  - "m_szCatalog"
  - "m_szDescription"
  - "m_szName"
  - "m_szSchema"
  - "m_szType"
  - "TABLE_CATALOG"
  - "TABLE_GUID"
  - "TABLE_NAME"
  - "TABLE_SCHEMA"
ms.assetid: 57670f1b-ba99-43b0-b406-4c75b44f14f6
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTables, CTableInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызовите **CTables** класс typedef для реализации его класс **CTableInfo** параметра.  
  
## Заметки  
 Дополнительные сведения см. в разделе [Классы набора строк схемы и классах typedef](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md) при использовании классов typedef.  
  
 Этот класс задает права в таблицах, указанных в каталоге, которые доступны тому или иному предоставленным или заданных пользователем.  
  
 В следующей таблице перечислены элементы данных класса и соответствующие столбцы OLE DB.  В разделе [Набор строк ТАБЛИЦ](https://msdn.microsoft.com/en-us/library/ms716980.aspx) справочника *программиста OLE DB* дополнительные сведения о схеме и столбцам.  
  
|Элементы данных|Столбцы OLE DB|  
|---------------------|--------------------|  
|m\_szCatalog|TABLE\_CATALOG|  
|m\_szSchema|TABLE\_SCHEMA|  
|m\_szName|TABLE\_NAME|  
|m\_szType|TABLE\_TYPE|  
|m\_guidTable|TABLE\_GUID|  
|m\_szDescription|DESCRIPTION|  
  
## Требования  
 **Header:**  atldbsch.h  
  
## См. также  
 [Класс CRestrictions](../Topic/CRestrictions%20Class.md)