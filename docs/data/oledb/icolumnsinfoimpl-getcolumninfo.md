---
title: "IColumnsInfoImpl::GetColumnInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetColumnInfo"
  - "ATL::IColumnsInfoImpl::GetColumnInfo"
  - "ATL.IColumnsInfoImpl.GetColumnInfo"
  - "ATL::IColumnsInfoImpl<T>::GetColumnInfo"
  - "IColumnsInfoImpl::GetColumnInfo"
  - "IColumnsInfoImpl<T>::GetColumnInfo"
  - "IColumnsInfoImpl.GetColumnInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetColumnInfo - метод"
ms.assetid: a6739a39-7402-496a-b544-a5b1ed05fadf
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IColumnsInfoImpl::GetColumnInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает метаданные столбца, требуемые большинством объектов\-получателей.  
  
## Синтаксис  
  
```  
  
      STDMETHOD (GetColumnInfo)(  
   DBORDINAL* pcColumns,  
   DBCOLUMNINFO** prgInfo,  
   OLECHAR** ppStringsBuffer   
);  
```  
  
#### Параметры  
 В разделе [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) справочника *программиста OLE DB*.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)   
 [IColumnsInfoImpl::MapColumnIDs](../../data/oledb/icolumnsinfoimpl-mapcolumnids.md)