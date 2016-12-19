---
title: "Математические константы | Microsoft Docs"
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
  - "c.constants"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_USE_MATH_DEFINES - константа"
  - "константы, математические"
  - "M_1_PI - константа"
  - "M_2_PI - константа"
  - "M_2_SQRTPI - константа"
  - "M_E - константа"
  - "M_LN10 - константа"
  - "M_LN2 - константа"
  - "M_LOG10E - константа"
  - "M_LOG2E - константа"
  - "M_PI - константа"
  - "M_PI_2 - константа"
  - "M_PI_4 - константа"
  - "M_SQRT1_2 - константа"
  - "M_SQRT2 - константа"
  - "математические константы"
  - "USE_MATH_DEFINES - константа"
ms.assetid: db533c3f-6ae8-4520-9d35-c8fabbef3529
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Математические константы
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
#define _USE_MATH_DEFINES // for C++  
#include <cmath>  
  
#define _USE_MATH_DEFINES // for C  
#include <math.h>  
```  
  
## Заметки  
 Следующие символы определены для значений указываемых ими выражений:  
  
|Символ|Выражение|Значение|  
|------------|---------------|--------------|  
|M\_E|e|2.71828182845904523536|  
|M\_LOG2E|log2\(e\)|1.44269504088896340736|  
|M\_LOG10E|log10\(e\)|0.434294481903251827651|  
|M\_LN2|ln\(2\)|0.693147180559945309417|  
|M\_LN10|ln\(10\)|2.30258509299404568402|  
|M\_PI|pi|3.14159265358979323846|  
|M\_PI\_2|pi\/2|1.57079632679489661923|  
|M\_PI\_4|pi\/4|0.785398163397448309616|  
|M\_1\_PI|1\/pi|0.318309886183790671538|  
|M\_2\_PI|2\/pi|0.636619772367581343076|  
|M\_2\_SQRTPI|2\/sqrt\(pi\)|1.12837916709551257390|  
|M\_SQRT2|sqrt\(2\)|1.41421356237309504880|  
|M\_SQRT1\_2|1\/sqrt\(2\)|0.707106781186547524401|  
  
 Математические константы не определены в стандарте C\/C\+\+.  Чтобы использовать их, необходимо сначала определить `_USE_MATH_DEFINES`, а затем включить cmath или math.h.  
  
 Файл ATLComTime.h включает math.h, когда проект создан в итоговом режиме.  При использовании одной или нескольких математических констант в проекте, который также включает ATLComTime.h, необходимо определить `_USE_MATH_DEFINES` до включения ATLComTime.h.  
  
## См. также  
 [Глобальные константы](../c-runtime-library/global-constants.md)