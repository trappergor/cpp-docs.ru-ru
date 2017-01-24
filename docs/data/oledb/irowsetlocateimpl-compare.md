---
title: "IRowsetLocateImpl::Compare | Microsoft Docs"
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
  - "ATL.IRowsetLocateImpl.Compare"
  - "IRowsetLocateImpl::Compare"
  - "IRowsetLocateImpl.Compare"
  - "ATL::IRowsetLocateImpl::Compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Compare - метод"
ms.assetid: 6f84052c-c68c-480a-982f-03748faa7d5d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetLocateImpl::Compare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сравнивает 2 закладки.  
  
## Синтаксис  
  
```  
  
      STDMETHOD ( Compare )(  
   HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmark1,  
   const BYTE* pBookmark1,  
   DBBKMARK cbBookmark2,  
   const BYTE* pBookmark2,  
   DBCOMPARE* pComparison   
);  
```  
  
#### Параметры  
 В разделе [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx) справочника *программиста OLE DB*.  
  
## Заметки  
 Любая из закладок может быть стандартным [стандартная закладки](https://msdn.microsoft.com/en-us/library/ms712954.aspx) базы данных заданным OLE \(**DBBMK\_FIRST**, **DBBMK\_LAST** или **DBBMK\_INVALID**\).  Значение, возвращаемое в `pComparison` показана связь между 2 закладками.  
  
-   **DBCOMPARE\_LT** \(`cbBookmark1` перед `cbBookmark2`\).  
  
-   **DBCOMPARE\_EQ** \(`cbBookmark1` равно `cbBookmark2`\).  
  
-   **DBCOMPARE\_GT** \(`cbBookmark1` после `cbBookmark2`\).  
  
-   **DBCOMPARE\_NE** \(закладки равны и не упорядочены\).  
  
-   **DBCOMPARE\_NOTCOMPARABLE** \(закладки нельзя сравнивать\).  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)