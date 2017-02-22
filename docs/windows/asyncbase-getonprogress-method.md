---
title: "Метод AsyncBase::GetOnProgress | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::GetOnProgress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetOnProgress - метод"
ms.assetid: 286ddc9c-3e30-41a2-8e8b-e53d3fb0649d
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод AsyncBase::GetOnProgress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Копирует адрес текущего прогресса обработчика событий завершения в указанную переменную.  
  
## Синтаксис  
  
```  
STDMETHOD(  
   GetOnProgress  
)(TProgress** progressHandler);  
```  
  
#### Параметры  
 `progressHandler`  
 Расположение, в котором сохраняется адрес текущего обработчика событий прогресса.  
  
## Возвращаемое значение  
 Значение S\_ОК в случае успеха; в противном случае — значение E\_ILLEGAL\_METHOD\_CALL.  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)