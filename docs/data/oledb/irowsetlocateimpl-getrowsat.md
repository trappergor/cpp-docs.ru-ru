---
title: "IRowsetLocateImpl::GetRowsAt | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetRowsAt"
  - "IRowsetLocateImpl.GetRowsAt"
  - "ATL::IRowsetLocateImpl::GetRowsAt"
  - "IRowsetLocateImpl::GetRowsAt"
  - "ATL.IRowsetLocateImpl.GetRowsAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRowsAt - метод"
ms.assetid: 6aeb09dc-3aa8-4729-97a8-144dd27063f7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetLocateImpl::GetRowsAt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получение строк, начиная со строки, заданной смещением от закладки.  
  
## Синтаксис  
  
```  
  
      STDMETHOD ( GetRowsAt )(  
   HWATCHREGION /* hReserved1 */,  
   HCHAPTER hReserved2,  
   DBBKMARK cbBookmark,  
   const BYTE* pBookmark,  
   DBROWOFFSET lRowsOffset,  
   DBROWCOUNT cRows,  
   DBCOUNTITEM* pcRowsObtained,  
   HROW** prghRows   
);  
```  
  
#### Параметры  
 В разделе [IRowsetLocate::GetRowsAt](https://msdn.microsoft.com/en-us/library/ms723031.aspx) справочника *программиста OLE DB*.  
  
## Заметки  
 Для получения с позиции курсора вместо этого используйте [IRowset::GetRowsAt](https://msdn.microsoft.com/en-us/library/ms723031.aspx).  
  
 `IRowsetLocateImpl::GetRowsAt` не изменяет положение курсора.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)   
 [IRowsetLocateImpl::GetRowsByBookmark](../../data/oledb/irowsetlocateimpl-getrowsbybookmark.md)