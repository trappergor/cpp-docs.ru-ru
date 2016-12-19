---
title: "operator . | Microsoft Docs"
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
  - "operator ."
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "dot operator (.)"
  - "operator ."
  - ". operator"
ms.assetid: 468ea0c8-5b08-47be-991b-38abacb77611
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# operator .
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает первый оператор *Выражение* с учетом смещения *поле* в его структуры или объединения.  Второй оператор возвращает значение в заданном расположении, к которым следуют *регистр* с учетом смещения *поле* в его структуры или объединения.  
  
## Синтаксис  
  
```  
  
      expression  
      . field [[. field]]...  
[register]. field [[. field]]...  
```  
  
## См. также  
 [Operators Reference](../Topic/Operators%20Reference.md)