---
title: "CBulkRowset::AddRefRows | Microsoft Docs"
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
  - "CBulkRowset::AddRefRows"
  - "AddRefRows"
  - "CBulkRowset.AddRefRows"
  - "ATL.CBulkRowset<TAccessor>.AddRefRows"
  - "ATL::CBulkRowset::AddRefRows"
  - "CBulkRowset<TAccessor>::AddRefRows"
  - "ATL.CBulkRowset.AddRefRows"
  - "ATL::CBulkRowset<TAccessor>::AddRefRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRefRows - метод"
ms.assetid: 014be991-50f8-4377-ba16-fec80b54b406
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBulkRowset::AddRefRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызывает метод [IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx), чтобы увеличить значение счетчика ссылок для всех строк в данный момент, извлеченных из навального набора строк.  
  
## Синтаксис  
  
```  
  
HRESULT AddRefRows( ) throw( );  
  
```  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CBulkRowset](../Topic/CBulkRowset%20Class.md)   
 [CBulkRowset::ReleaseRows](../Topic/CBulkRowset::ReleaseRows.md)