---
title: "GOTO (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "goto"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GOTO directive"
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# GOTO (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Передает сборку в помеченной линии .macrolabel.  
  
## Синтаксис  
  
```  
  
GOTO   
macrolabel  
  
```  
  
## Заметки  
 **GOTO** разрешает только внутри  [макроопределение](../Topic/MACRO.md)"  [ДЛЯ](../../assembler/masm/for-masm.md)"  [FORC](../Topic/FORC.md)"  [Повторение](../../assembler/masm/repeat.md)и  **ПОКА** блоки.  Метка должна быть единственной директивой на линии и должна стоять ведущим двоеточием.  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)