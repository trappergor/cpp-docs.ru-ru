---
title: "YMMWORD | Microsoft Docs"
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
  - "YMMWORD"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "YMMWORD directive"
ms.assetid: 955a7d23-6150-4056-befc-7f72e8258ecb
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# YMMWORD
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используется для операндов мультимедиа с 256 бита Intel дополнительные инструкции расширений вектора \(AVX\).  
  
## Синтаксис  
  
```  
YMMWORD  
```  
  
## Заметки  
 `YMMWORD` должно представлять один и тот же тип, что `__m256` для встроенных функций AVX.  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)