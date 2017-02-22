---
title: "INCLUDELIB (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "INCLUDELIB"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "INCLUDELIB directive"
ms.assetid: 5455d004-8202-4b57-93f3-9aa66f133a2d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# INCLUDELIB (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сообщает компоновщику, что текущий модуль должен быть связан с *libraryname*.  
  
## Синтаксис  
  
```  
  
INCLUDELIB libraryname  
```  
  
## Заметки  
 *libraryname* быть заключен в угловые скобки, если он включает обратную косую черту, точку с запятой, символ " больше чем ", " меньше символ, одинарная кавычка, либо двойная кавычка.  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)