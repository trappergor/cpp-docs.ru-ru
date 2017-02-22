---
title: "CProcedureColumns, CProcedureColumnInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "m_guidType"
  - "CProcedureColumnInfo"
  - "IS_NULLABLE"
  - "m_szCatalog"
  - "m_nRowsetNumber"
  - "m_nColumnPropID"
  - "ORDINAL_POSITION"
  - "m_nOrdinalPosition"
  - "COLUMN_GUID"
  - "m_szColumnName"
  - "NUMERIC_PRECISION"
  - "m_nDataType"
  - "m_szSchema"
  - "CHARACTER_OCTET_LENGTH"
  - "NUMERIC_SCALE"
  - "COLUMN_PROPID"
  - "m_guidColumn"
  - "m_nMaxLength"
  - "CHARACTER_MAXIMUM_LENGTH"
  - "m_nPrecision"
  - "m_szName"
  - "CProcedureColumns"
  - "DATA_TYPE"
  - "m_nOctetLength"
  - "m_bIsNullable"
  - "m_nScale"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHARACTER_MAXIMUM_LENGTH"
  - "CHARACTER_OCTET_LENGTH"
  - "COLUMN_GUID"
  - "COLUMN_NAME"
  - "COLUMN_PROPID"
  - "CProcedureColumnInfo - класс параметров"
  - "CProcedureColumns typedef - класс"
  - "DATA_TYPE"
  - "DESCRIPTION - данные-член класса"
  - "IS_NULLABLE"
  - "m_bIsNullable"
  - "m_guidColumn"
  - "m_guidType"
  - "m_nColumnPropID"
  - "m_nDataType"
  - "m_nMaxLength"
  - "m_nOctetLength"
  - "m_nOrdinalPosition"
  - "m_nPrecision"
  - "m_nRowsetNumber"
  - "m_nScale"
  - "m_szCatalog"
  - "m_szColumnName"
  - "m_szDescription"
  - "m_szName"
  - "m_szSchema"
  - "NUMERIC_PRECISION"
  - "NUMERIC_SCALE"
  - "ORDINAL_POSITION"
ms.assetid: c82626c4-8047-4b9c-b342-e35bf37b7611
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CProcedureColumns, CProcedureColumnInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызовите **CProcedureColumns** класс typedef для реализации его класс **CProcedureColumnInfo** параметра.  
  
## Заметки  
 Дополнительные сведения см. в разделе [Классы набора строк схемы и классах typedef](../Topic/Schema%20Rowset%20Classes%20and%20Typedef%20Classes.md) при использовании классов typedef.  
  
 Этот класс возвращает сведения о столбцах наборов строк, возвращаемых процедурами.  
  
 В следующей таблице перечислены элементы данных класса и соответствующие столбцы OLE DB.  В разделе [Набор строк PROCEDURE\_COLUMNS](https://msdn.microsoft.com/en-us/library/ms723092.aspx) справочника *программиста OLE DB* дополнительные сведения о схеме и столбцам.  
  
|Элементы данных|Столбцы OLE DB|  
|---------------------|--------------------|  
|m\_szCatalog|PROCEDURE\_CATALOG|  
|m\_szSchema|PROCEDURE\_SCHEMA|  
|m\_szName|PROCEDURE\_NAME|  
|m\_szColumnName|COLUMN\_NAME|  
|m\_guidColumn|COLUMN\_GUID|  
|m\_nColumnPropID|COLUMN\_PROPID|  
|m\_nRowsetNumber|ROWSET\_NUMBER|  
|m\_nOrdinalPosition|ORDINAL\_POSITION|  
|m\_bIsNullable|IS\_NULLABLE|  
|m\_nDataType|DATA\_TYPE|  
|m\_guidType|TYPE\_GUID|  
|m\_nMaxLength|CHARACTER\_MAXIMUM\_LENGTH|  
|m\_nOctetLength|CHARACTER\_OCTET\_LENGTH|  
|m\_nPrecision|NUMERIC\_PRECISION|  
|m\_nScale|NUMERIC\_SCALE|  
|m\_szDescription|DESCRIPTION|  
  
## Требования  
 **Header:**  atldbsch.h  
  
## См. также  
 [Класс CRestrictions](../Topic/CRestrictions%20Class.md)