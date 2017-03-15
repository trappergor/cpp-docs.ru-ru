---
title: "Метод AsyncBase::get_Id | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::get_Id"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "get_Id - метод"
ms.assetid: 591d8366-ea76-4deb-9278-9d3bc394a42b
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод AsyncBase::get_Id
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Извлекает дескриптор асинхронной операции.  
  
## Синтаксис  
  
```  
STDMETHOD(  
   get_Id  
)(unsigned int *id) override;  
```  
  
#### Параметры  
 `id`  
 Ячейка памяти, в которой будет храниться дескриптор.  
  
## Возвращаемое значение  
 Значение S\_ОК в случае успеха; в противном случае — значение E\_ILLEGAL\_METHOD\_CALL.  
  
## Примечания  
 Этот метод реализует IAsyncInfo::get\_Id.  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)