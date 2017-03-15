---
title: "Каковы издержки при наследовании классов от CObject? | Microsoft Docs"
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
  - "CObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CObject - класс, издержки производных классов"
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Каковы издержки при наследовании классов от CObject?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Рабочая нагрузка в наследование от класса [CObject](../Topic/CObject%20Class.md) минимальна.  Производный класс наследует только 4 виртуальных функций и одного объекта [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md).  
  
## См. также  
 [Класс CObject. Часто задаваемые вопросы](../mfc/cobject-class-frequently-asked-questions.md)