---
title: "HUGE_VAL, _HUGE | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_HUGE"
apilocation: 
  - "msvcrt.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_HUGE"
  - "HUGE_VAL"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_HUGE - константа"
  - "HUGE_VAL - константа"
  - "двойное значение"
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# HUGE_VAL, _HUGE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <math.h>  
  
```  
  
## Заметки  
 `HUGE_VAL` является максимальным представимым значением double.  Это значение возвращается множеством математических функций времени выполнения при возникновении ошибки.  Для некоторых функций возвращается –`HUGE_VAL`.  `HUGE_VAL` определяется как `_HUGE`, но математические функции времени выполнения возвращают `HUGE_VAL`.  Необходимо также использовать в коде `HUGE_VAL`, для согласованности.  
  
## См. также  
 [Глобальные константы](../c-runtime-library/global-constants.md)