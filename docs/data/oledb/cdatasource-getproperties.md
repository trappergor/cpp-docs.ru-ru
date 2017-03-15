---
title: "CDataSource::GetProperties | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataSource::GetProperties"
  - "ATL.CDataSource.GetProperties"
  - "CDataSource.GetProperties"
  - "ATL::CDataSource::GetProperties"
  - "GetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProperties - метод"
ms.assetid: ffaecc17-9fe7-449e-94d6-43d31ad06cfc
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CDataSource::GetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает сведения о свойствах запрос для объекта подключенного источника данных.  
  
## Синтаксис  
  
```  
  
      HRESULT GetProperties(   
   ULONG ulPropIDSets,   
   const DBPROPIDSET* pPropIDSet,   
   ULONG* pulPropertySets,   
   DBPROPSET** ppPropsets    
) const throw( );  
```  
  
#### Параметры  
 В разделе [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) справочника *программиста по OLE DB* в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Чтобы получить отдельное свойство, используйте [GetProperty](../Topic/CDataSource::GetProperty.md).  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CDataSource](../Topic/CDataSource%20Class.md)