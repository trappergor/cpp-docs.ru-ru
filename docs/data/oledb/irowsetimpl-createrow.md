---
title: "IRowsetImpl::CreateRow | Microsoft Docs"
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
  - "IRowsetImpl.CreateRow"
  - "ATL.IRowsetImpl.CreateRow"
  - "ATL::IRowsetImpl::CreateRow"
  - "CreateRow"
  - "IRowsetImpl::CreateRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateRow - метод"
ms.assetid: b01c430c-9484-4fef-a6cf-a2e8d9d99130
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetImpl::CreateRow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Вспомогательный метод [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) вызывается, чтобы выделить новый объект **HROW**.  
  
## Синтаксис  
  
```  
  
      HRESULT CreateRow(  
   DBROWOFFSET lRowsOffset,  
   DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows   
);  
```  
  
#### Параметры  
 *lRowsOffset*  
 Позиция курсора создаваемому строки.  
  
 *cRowsObtained*  
 Ссылка прошла пользователю, указывающее количество создаваемых строк.  
  
 *rgRows*  
 Массив объектов **HROW**, возвращаемый вызывающему объекту с созданными последними дескрипторами строк.  
  
## Заметки  
 Если строка существует, этот метод вызывает метод [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) и возвращают.  В противном случае она выделяет новый экземпляр переменной шаблона RowClass и добавляет ее в [m\_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md).  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IRowsetImpl](../Topic/IRowsetImpl%20Class.md)