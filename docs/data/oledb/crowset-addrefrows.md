---
title: "CRowset::AddRefRows | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowset<TAccessor>.AddRefRows"
  - "CRowset.AddRefRows"
  - "ATL.CRowset.AddRefRows"
  - "AddRefRows"
  - "CRowset::AddRefRows"
  - "CRowset<TAccessor>::AddRefRows"
  - "ATL::CRowset::AddRefRows"
  - "ATL.CRowset<TAccessor>.AddRefRows"
  - "ATL::CRowset<TAccessor>::AddRefRows"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddRefRows - метод"
ms.assetid: 590b5a24-870f-4c42-b0c8-28491f368a82
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::AddRefRows
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вызовы [IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) увеличивающий счетчик ссылок \(.\), связанные с дескриптором текущей строки.  
  
## Синтаксис  
  
```  
  
HRESULT AddRefRows( ) throw( );  
  
```  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Этот метод увеличивает счетчик ссылок для дескриптора текущей строки.  Вызов [ReleaseRows](../Topic/CRowset::ReleaseRows.md), чтобы уменьшить число.  Строки возвращаются методами перемещения имеют одного счетчика ссылок.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CRowset](../Topic/CRowset%20Class.md)   
 [CRowset::ReleaseRows](../Topic/CRowset::ReleaseRows.md)