---
title: "IDBCreateCommandImpl::CreateCommand | Microsoft Docs"
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
  - "IDBCreateCommandImpl.CreateCommand"
  - "CreateCommand"
  - "IDBCreateCommandImpl::CreateCommand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateCommand - метод"
ms.assetid: 50ffbf8b-2c07-4bcb-96c5-ffce4519c7f7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IDBCreateCommandImpl::CreateCommand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает новую команду и возвращает запрошенный интерфейс.  
  
## Синтаксис  
  
```  
  
      STDMETHOD(CreateCommand)(   
   IUnknown * pUnkOuter,   
   REFIID riid,   
   IUnknown ** ppvCommand    
);  
```  
  
#### Параметры  
 В разделе [IDBCreateCommand::CreateCommand](https://msdn.microsoft.com/en-us/library/ms709772.aspx) справочника *программиста OLE DB*.  
  
 Некоторые параметры соответствуют *параметрам ссылочным программиста OLE DB* других имен, описанных в **IDBCreateCommand::CreateCommand**:  
  
|Параметры шаблонов OLE DB|*Ссылочные параметры программиста OLE DB*|  
|-------------------------------|-----------------------------------------------|  
|*ppvCommand*|*ppCommand*|  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)