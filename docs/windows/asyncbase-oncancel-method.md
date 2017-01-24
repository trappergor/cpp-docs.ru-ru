---
title: "Метод AsyncBase::OnCancel | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase::OnCancel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnCancel - метод"
ms.assetid: 4bd0b68e-a9df-4913-9f6c-e093ed55c3f9
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод AsyncBase::OnCancel
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При переопределении в производном классе отменяет асинхронную операцию.  
  
## Синтаксис  
  
```  
virtual void OnCancel(  
   void  
) = 0;  
```  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)   
 [Метод AsyncBase::Cancel](../Topic/AsyncBase::Cancel%20Method.md)