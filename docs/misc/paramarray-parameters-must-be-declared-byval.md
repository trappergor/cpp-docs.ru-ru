---
title: "Параметры ParamArray должны объявляться как ByVal | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30667"
  - "bc30667"
helpviewer_keywords: 
  - "BC30667"
ms.assetid: 583e231f-a4c9-47aa-ae37-7bac43b0b318
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Параметры ParamArray должны объявляться как ByVal
Параметры `ParamArray` не могут использовать модификатор `ByRef`.  
  
 **Идентификатор ошибки**: BC30667  
  
### Исправление ошибки  
  
-   Объявите параметры `ParamArray` с использованием модификатора `ByVal`.  
  
## См. также  
 [ParamArray](../Topic/ParamArray%20\(Visual%20Basic\).md)   
 [ByRef](../Topic/ByRef%20\(Visual%20Basic\).md)   
 [ByVal](../Topic/ByVal%20\(Visual%20Basic\).md)