---
title: "Метод AsyncBase::FireCompletion | Microsoft Docs"
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
  - "async/Microsoft::WRL::AsyncBase::FireCompletion"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FireCompletion - метод"
ms.assetid: b5e29d6d-52e7-4148-a7f3-a313b1359819
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод AsyncBase::FireCompletion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Вызывает обработчик событий завершения или сбрасывает внутренний делегат выполнения.  
  
## Синтаксис  
  
```  
void FireCompletion(  
   void  
) override;  
  
virtual void FireCompletion();  
```  
  
## Примечания  
 Первая версия FireCompletion\(\) сбрасывает переменную внутреннего делегата выполнения.  Вторая версия вызывает обработчик событий завершения если асинхронная операция завершена.  
  
## Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)