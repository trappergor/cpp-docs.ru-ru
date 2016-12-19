---
title: "IRowsetChangeImpl::FlushData | Microsoft Docs"
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
  - "IRowsetChangeImpl::FlushData"
  - "IRowsetChangeImpl.FlushData"
  - "FlushData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FlushData - метод"
ms.assetid: fd4bc73b-bc25-4aab-90d5-0bed92670c88
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetChangeImpl::FlushData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Overidden поставщиком для сохранения данных в его хранилище.  
  
## Синтаксис  
  
```  
  
      HRESULT FlushData(  
   HROW hRowToFlush,  
   HACCESSOR hAccessorToFlush   
);  
```  
  
#### Параметры  
 *hRowToFlush*  
 \[in\] дескриптор строки для данных.  Тип этой строки определяется на основе аргумента шаблона *RowClass* класса `IRowsetImpl` \(`CSimpleRow` по умолчанию\).  
  
 *hAccessorToFlush*  
 \[in\] дескриптор метода доступа, которые содержат информацию о привязке и сведения о типе в его **PROVIDER\_MAP** \(см. раздел [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)\).  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)