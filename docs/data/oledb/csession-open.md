---
title: "CSession::Open | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CSession::Open"
  - "CSession::Open"
  - "CSession.Open"
  - "ATL.CSession.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open - метод"
ms.assetid: c2050c2c-9817-4857-be49-189f346968f6
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CSession::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Открывает новый сеанс для объекта источника данных.  
  
## Синтаксис  
  
```  
  
      HRESULT Open(  
   const CDataSource& ds,  
   DBPROPSET *pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw( );  
```  
  
#### Параметры  
 `ds`  
 \[in\] источник данных, для которого сеанс, раскрытым.  
  
 *pPropSet*  
 \[in\] указатель на массив структур [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx), содержащий свойства и значения, используемые для задания.  В разделе [Наборы свойств и группы свойств](https://msdn.microsoft.com/en-us/library/ms713696.aspx) справочника *программиста по OLE DB* в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `ulPropSets`  
 \[in\] количество структур [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx), переданных в аргумент *pPropSet*.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Необходимо открыть объект источника данных с помощью [CDataSource::Open](../../data/oledb/cdatasource-open.md) перед передачей их `CSession::Open`.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [класс CSession](../../data/oledb/csession-class.md)