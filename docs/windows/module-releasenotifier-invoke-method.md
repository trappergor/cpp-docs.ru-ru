---
title: "Метод Module::ReleaseNotifier::Invoke | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::ReleaseNotifier::Invoke"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Invoke - метод"
ms.assetid: f62686fe-74bf-482b-a46b-6a3c09b80e7e
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Метод Module::ReleaseNotifier::Invoke
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В случае реализации вызывает обработчик событий при освобождении последнего объекта в модуле.  
  
## Синтаксис  
  
```  
virtual void Invoke() = 0;  
```  
  
## Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Класс Module::ReleaseNotifier](../Topic/Module::ReleaseNotifier%20Class.md)