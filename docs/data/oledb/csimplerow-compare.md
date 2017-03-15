---
title: "CSimpleRow::Compare | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CSimpleRow.Compare"
  - "CSimpleRow::Compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Compare - метод"
ms.assetid: 0bb65f09-c7bc-449b-aa4e-c828cac13510
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CSimpleRow::Compare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сравнивает 2 строки для просмотра, если они ссылаются на один и тот же экземпляр строки.  
  
## Синтаксис  
  
```  
  
      HRESULT Compare(   
   CSimpleRow* pRow    
);  
```  
  
#### Параметры  
 `pRow`  
 Указатель на объект `CSimpleRow`.  
  
## Возвращаемое значение  
 `HRESULT` значение, обычно `S_OK`, 2 строки один и тот же экземпляр строки, или **S\_FALSE**, показывающее, 2 строки другое.  В разделе [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) справочника *программиста OLE DB* для других возможных возвращаемых значений.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс CSimpleRow](../Topic/CSimpleRow%20Class.md)   
 [CSimpleRow::ReleaseRow](../Topic/CSimpleRow::ReleaseRow.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)