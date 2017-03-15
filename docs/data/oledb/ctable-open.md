---
title: "CTable::Open | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CTable.Open"
  - "ATL::CTable::Open"
  - "CTable::Open"
  - "CTable.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open - метод"
ms.assetid: 5d006d95-74d7-4e2b-b243-a33bc53b5455
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CTable::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Открытия таблицы.  
  
## Синтаксис  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCWSTR wszTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   LPCSTR szTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   DBID& dbid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
```  
  
#### Параметры  
 `session`  
 \[in\] сеанс, для которого следует создать таблицу.  
  
 *wszTableName*  
 \[in\] имя таблицы, которую необходимо открыть, переданное в качестве строки юникод.  
  
 *szTableName*  
 \[in\] имя таблицы, которую необходимо открыть, переданное в качестве строки ANSI.  
  
 *dbid*  
 \[in\] **DBID** таблицы, которую необходимо открыть.  
  
 *pPropSet*  
 \[in\] указатель на массив структур [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx), содержащий свойства и значения, используемые для задания.  В разделе [Наборы свойств и группы свойств](https://msdn.microsoft.com/en-us/library/ms713696.aspx) справочника *программиста по OLE DB* в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  Значение по умолчанию NULL не определяет никаких свойств.  
  
 `ulPropSets`  
 \[in\] количество структур [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx), переданных в аргумент *pPropSet*.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Дополнительные сведения см. в разделе [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) справочника *программиста OLE DB*.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CTable](../../data/oledb/ctable-class.md)