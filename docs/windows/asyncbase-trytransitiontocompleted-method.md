---
title: "Метод AsyncBase::TryTransitionToCompleted | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::TryTransitionToCompleted"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TryTransitionToCompleted - метод"
ms.assetid: 8d038e0a-47ec-4cfc-8aeb-6821282df67a
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод AsyncBase::TryTransitionToCompleted
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Показывает, выполнена ли текущая асинхронная операция.  
  
## Синтаксис  
  
```  
bool TryTransitionToCompleted(  
   void  
);  
```  
  
## Возвращаемое значение  
 Значение `true`, если асинхронная операция завершилась; в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)