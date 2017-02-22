---
title: "PAGE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PAGE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Page directive"
ms.assetid: 6654c094-c1f7-4d10-8d9d-902ddd1ac27e
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# PAGE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Первая директива задает линию *длина* и *ширина* пример программы.  Если аргументы не предоставляются, то создает разрыв страницы.  Вторая директива увеличивает номер секции и сбросить номер страницы до 1.  
  
## Синтаксис  
  
```  
  
      PAGE [[[[length]], width]]  
PAGE +  
```  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)