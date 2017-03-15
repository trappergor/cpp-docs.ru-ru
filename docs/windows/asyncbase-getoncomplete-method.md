---
title: "Метод AsyncBase::GetOnComplete | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::GetOnComplete"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetOnComplete - метод"
ms.assetid: f06ae02d-9a88-41d2-b749-bdc1a7ff8748
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод AsyncBase::GetOnComplete
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Копирует адрес текущего обработчика событий завершения в указанную переменную.  
  
## Синтаксис  
  
```  
STDMETHOD(  
   GetOnComplete  
)(TComplete** completeHandler);  
```  
  
#### Параметры  
 `completeHandler`  
 Расположение, в котором сохраняется адрес текущего обработчика событий завершения.  
  
## Возвращаемое значение  
 Значение S\_ОК в случае успеха; в противном случае — значение E\_ILLEGAL\_METHOD\_CALL.  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)