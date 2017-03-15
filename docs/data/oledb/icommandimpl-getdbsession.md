---
title: "ICommandImpl::GetDBSession | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandImpl::GetDBSession"
  - "GetDBSession"
  - "ICommandImpl.GetDBSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetDBSession - метод"
ms.assetid: e5b1cb13-453f-4698-90bf-f6bfe6814a54
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ICommandImpl::GetDBSession
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает указатель интерфейса к сеансу, создавшего команду.  
  
## Синтаксис  
  
```  
  
      STDMETHOD (GetDBSession) (  
   REFIID riid,  
   IUnknown** ppSession   
);  
```  
  
#### Параметры  
 В разделе [ICommand::GetDBSession](https://msdn.microsoft.com/en-us/library/ms719622.aspx) справочника *программиста OLE DB*.  
  
## Заметки  
 Используются для извлечения свойства из сеанса.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс ICommandImpl](../Topic/ICommandImpl%20Class.md)