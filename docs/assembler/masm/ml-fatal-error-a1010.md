---
title: "ML Fatal Error A1010 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A1010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1010"
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Fatal Error A1010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**несогласованная директива вложение блока:**  
  
 Начало блока не имело соответствующее конец или конец блока не имеет соответствующего начало.  Одно из следующих действий может быть включено:  
  
-   Высокоуровневая как директива [.IF](../Topic/.IF.md)"  [.REPEAT](../../assembler/masm/dot-repeat.md)или  [.WHILE](../../assembler/masm/dot-while.md).  
  
-   Директива условный\-сборки как [IF](../../assembler/masm/if-masm.md)"  [Повторение](../../assembler/masm/repeat.md)или  **ПОКА**.  
  
-   Определение структуры или объединения.  
  
-   Определение процедуры.  
  
-   Определение сегмента.  
  
-   A POPCONTEXT директива.  
  
-   Условный\-сборки, как директива [ELSE](../Topic/ELSE%20\(MASM\).md)"  [ELSEIF](../../assembler/masm/elseif-masm.md)или  **endif** без соответствующей  [IF](../../assembler/masm/if-masm.md).  
  
## См. также  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)