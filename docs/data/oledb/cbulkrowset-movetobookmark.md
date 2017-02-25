---
title: "CBulkRowset::MoveToBookmark | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBulkRowset<TAccessor>::MoveToBookmark"
  - "CBulkRowset.MoveToBookmark"
  - "MoveToBookmark"
  - "ATL.CBulkRowset.MoveToBookmark"
  - "CBulkRowset::MoveToBookmark"
  - "ATL::CBulkRowset<TAccessor>::MoveToBookmark"
  - "ATL::CBulkRowset::MoveToBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToBookmark - метод"
ms.assetid: 76aab025-819e-4ecd-ae0a-d8d3fb2d2099
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CBulkRowset::MoveToBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Доступа к строке, помеченной закладкой или строка с указанным смещением \(`lSkip`\) из этой закладки.  
  
## Синтаксис  
  
```  
  
      HRESULT MoveToBookmark(  
   const CBookmarkBase& bookmark,  
   DBCOUNTITEM lSkip = 0   
) throw( );  
```  
  
#### Параметры  
 `bookmark`  
 \[in\] закладки a пометки расположение, из которого необходимо получить данные.  
  
 `lSkip`  
 \[in\] количество номера строк из закладок в строке целевого объекта.  Если `lSkip` ноль, то первая строка удаленный доступ полученная строка создать закладку.  Если `lSkip` 1, то первая строка удаленный доступ полученная строка после создать закладку строки.  Если `lSkip` — 1, полученная удаленный доступ первая строка является строкой перед строкой создать закладку.  
  
## Возвращаемое значение  
 В разделе [IRowset::GetData](https://msdn.microsoft.com/en-us/library/ms716988.aspx) справочника *программиста OLE DB*.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CBulkRowset](../Topic/CBulkRowset%20Class.md)