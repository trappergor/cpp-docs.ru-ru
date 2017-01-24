---
title: "CManualAccessor::AddBindEntry | Microsoft Docs"
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
  - "ATL::CManualAccessor::AddBindEntry"
  - "ATL.CManualAccessor.AddBindEntry"
  - "CManualAccessor::AddBindEntry"
  - "AddBindEntry"
  - "CManualAccessor.AddBindEntry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddBindEntry - метод"
ms.assetid: 8556dda9-dda1-4f67-96bc-6031e6c6a271
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CManualAccessor::AddBindEntry
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Добавляет запись привязки к выходным столбцам.  
  
## Синтаксис  
  
```  
  
      void AddBindEntry(  
   DBORDINAL nOrdinal,  
   DBTYPE wType,  
   DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL   
) throw ( );  
```  
  
#### Параметры  
 В разделе [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) справочника *программиста OLE DB*.  
  
 `nOrdinal`  
 \[in\] число столбцов.  
  
 `wType`  
 \[in\] тип данных.  
  
 `nColumnSize`  
 \[in\] размер столбца в байтах.  
  
 `pData`  
 \[in\] указатель на данные, хранящиеся в столбце буфера.  
  
 `pLength`  
 \[in\] указатель на длину поля, если это необходимо.  
  
 `pStatus`  
 \[in\] указатель на переменную, привязываемая к состоянию столбца, если это необходимо.  
  
## Заметки  
 Чтобы воспользоваться этой функцией, нужно сначала вызовите метод [CreateAccessor](../Topic/CManualAccessor::CreateAccessor.md).  Можно добавить несколько записей, чем количество столбцов, указанное в `CreateAccessor`.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CManualAccessor](../Topic/CManualAccessor%20Class.md)   
 [Пример DBViewer](../../top/visual-cpp-samples.md)