---
title: "CRowsetImpl::SetCommandText | Microsoft Docs"
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
  - "CRowsetImpl.SetCommandText"
  - "CRowsetImpl::SetCommandText"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetCommandText - метод"
ms.assetid: e016d7df-c1a0-4dee-b19b-c876680221fd
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl::SetCommandText
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Проверяет и сохраняет **DBID** в слове 2 строк \([m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) и [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)\).  
  
## Синтаксис  
  
```  
  
      HRESULT CRowsetBaseImpl::SetCommandText(  
   DBID* pTableID,  
   DBID* pIndexID   
);  
```  
  
#### Параметры  
 `pTableID`  
 \[in\] указатель на **DBID**, представляющая идентификатор таблицы  
  
 `pIndexID`  
 \[in\] указатель на **DBID**, представляющий индекс идентификатор.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Метод **SetCommentText** был вызван `CreateRowset`, templatized статическим методом `IOpenRowsetImpl`.  
  
 Этот метод делегирует работу с помощью метода [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) и [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md) upcasted через указатель.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс CRowsetImpl](../../data/oledb/crowsetimpl-class.md)