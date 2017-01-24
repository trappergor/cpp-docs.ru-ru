---
title: "Метод AsyncBase::OnClose | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::OnClose"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnClose - метод"
ms.assetid: 96766450-c262-4611-8534-7d190b799142
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод AsyncBase::OnClose
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

При переопределении в производном классе закрывает асинхронную операцию.  
  
## Синтаксис  
  
```  
virtual void OnClose(  
   void  
) = 0;  
```  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)   
 [Метод AsyncBase::Close](../windows/asyncbase-close-method.md)