---
title: ".REPEAT | Microsoft Docs"
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
  - ".REPEAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".REPEAT directive"
ms.assetid: cb8ad8c6-587b-42f9-a0ad-b5316a24918c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .REPEAT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает код которого повторит выполнение блока выписки значение `condition` будет истинными.  [.UNTILCXZ](../../assembler/masm/dot-untilcxz.md), который будет true, если CX нулю, может быть заменено для  [.UNTIL](../../assembler/masm/dot-until.md).  `condition` необязательные с  **.UNTILCXZ**.  
  
## Синтаксис  
  
```  
  
   .REPEAT  
statements  
.UNTIL condition  
```  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)