---
title: "IRowsetImpl::m_bCanFetchBack | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetImpl.m_bCanFetchBack"
  - "ATL::IRowsetImpl::m_bCanFetchBack"
  - "IRowsetImpl.m_bCanFetchBack"
  - "IRowsetImpl::m_bCanFetchBack"
  - "m_bCanFetchBack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_bCanFetchBack"
ms.assetid: cfa007b0-7ba5-48a3-9d05-9f1916305fb7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::m_bCanFetchBack
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает, поддерживает ли поставщик обратно к.  
  
## Синтаксис  
  
```  
  
unsigned m_bCanFetchBack:1;  
  
```  
  
## Заметки  
 Связанный с **DBPROP\_CANFETCHBACKWARDS** свойство в группе **DBPROPSET\_ROWSET**.  Поставщик должен поддерживать **DBPROP\_CANFETCHBACKWARDS** для **m\_bCanFetchBackwards**, чтобы оно было справедливым.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IRowsetImpl](../Topic/IRowsetImpl%20Class.md)   
 [IRowsetImpl::m\_bCanScrollBack](../../data/oledb/irowsetimpl-m-bcanscrollback.md)