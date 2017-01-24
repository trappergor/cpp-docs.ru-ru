---
title: "IF (MASM) | Microsoft Docs"
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
  - "if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IF directive"
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# IF (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет сборку *ifstatements* If *expression1* ненулевое значение \- true \(\) или *elseifstatements* If *expression1* 0\) и false \(выкл. *expression2* \- true.  
  
## Синтаксис  
  
```  
  
   IF expression1  
ifstatements  
[[ELSEIF expression2  
   elseifstatements]]  
[[ELSE  
   elsestatements]]  
ENDIF  
```  
  
## Заметки  
 Следующие рекомендации могут быть заменены для [ELSEIF](../../assembler/masm/elseif-masm.md).  **ELSEIFB**"  **ELSEIFDEF**"  **ELSEIFDIF**"  **ELSEIFDIFI**"  **ELSEIFE**"  **ELSEIFIDN**"  **ELSEIFIDNI**"  **ELSEIFNB**и  **ELSEIFNDEF**.  При необходимости собрати *elsestatements* если предыдущее выражение значение false.  Обратите внимание, что выражения вычисляются во время сборки.  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)