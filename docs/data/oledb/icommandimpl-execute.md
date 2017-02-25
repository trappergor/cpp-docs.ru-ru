---
title: "ICommandImpl::Execute | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandImpl::Execute"
  - "ICommandImpl.Execute"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Execute - метод"
ms.assetid: 033e0d4e-256b-4eed-9215-70e0bebb768c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ICommandImpl::Execute
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выполняет команду.  
  
## Синтаксис  
  
```  
  
      HRESULT Execute(  
   IUnknown* pUnkOuter,  
   REFIID riid,  
   DBPARAMS* pParams,  
   DBROWCOUNT* pcRowsAffected,  
   IUnknown** ppRowset   
);  
```  
  
#### Параметры  
 В разделе [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) справочника *программиста OLE DB*.  
  
## Заметки  
 Требуемые исходящий интерфейс будет интерфейсом приобретенным из объекта набора строк, эта функция создает.  
  
 [CreateRowset](../Topic/ICommandImpl::CreateRowset.md) вызывает метод **Выполнить**.  Переопределите реализацию по умолчанию для создания более одного набора строк или предоставить свои собственные условия для создания различных наборов строк.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс ICommandImpl](../Topic/ICommandImpl%20Class.md)   
 [ICommandImpl::CancelExecution](../../data/oledb/icommandimpl-cancelexecution.md)