---
title: "DD | Microsoft Docs"
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
  - "dd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DD directive"
ms.assetid: 0c238628-2fe2-437e-979d-a90bdae7b478
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# DD
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Выделяет и инициализирует машинное двойное слово \(4 байта\) хранения для каждого `initializer`.  `DD` синоним   [dword](../../assembler/masm/dword.md).  
  
## Синтаксис  
  
```  
[[name]] DD initializer [[, initializer]]...  
```  
  
## Заметки  
 Может также использоваться как описатель типа в любом месте, где допустим тип.  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)