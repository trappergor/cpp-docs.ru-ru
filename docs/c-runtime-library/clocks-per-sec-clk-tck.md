---
title: "CLOCKS_PER_SEC, CLK_TCK | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CLOCKS_PER_SEC"
  - "CLK_TCK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLK_TCK - константа"
  - "CLOCKS_PER_SEC"
ms.assetid: bc285106-383d-44cb-91bf-276ad7de57bf
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# CLOCKS_PER_SEC, CLK_TCK
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <time.h>  
```  
  
## Заметки  
 Время в секундах — значение, возвращаемое функцией `clock`, разделенное на `CLOCKS_PER_SEC`.  `CLK_TCK` эквивалентно, но считается устаревшим.  
  
## См. также  
 [часы](../c-runtime-library/reference/clock.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)