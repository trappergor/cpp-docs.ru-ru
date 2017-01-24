---
title: "Константы математических ошибок | Microsoft Docs"
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
  - "_PLOSS"
  - "_UNDERFLOW"
  - "_TLOSS"
  - "_SING"
  - "_DOMAIN"
  - "_OVERFLOW"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_DOMAIN - константа"
  - "_OVERFLOW - константа"
  - "_PLOSS - константа"
  - "_SING - константа"
  - "_TLOSS - константа"
  - "_UNDERFLOW - константа"
  - "DOMAIN - константа"
  - "константы математических ошибок"
  - "OVERFLOW - константа"
  - "PLOSS - константа"
  - "SING - константа"
  - "TLOSS - константа"
  - "UNDERFLOW - константа"
ms.assetid: 4be933a6-674e-45a5-8ac9-090023542f5b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Константы математических ошибок
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <math.h>  
  
```  
  
## Заметки  
 Математические процедуры библиотеки времени выполнения могут генерировать константы математических ошибок.  
  
 Эти ошибки, описанные ниже, соответствуют типам исключений, определенным в MATH.H и возвращаются функцией `_matherr`, когда возникает математическая ошибка.  
  
|Константа|Значение|  
|---------------|--------------|  
|`_DOMAIN`|Значение аргумента функции находится вне домена функции.|  
|`_OVERFLOW`|Результат слишком велик для представления в качестве типа возвращаемого значения функции.|  
|`_PLOSS`|Произошла частичная потеря точности.|  
|`_SING`|Сингулярность аргумента: аргумент функции имеет недопустимое значение. \(Например, значение 0 передается в функцию, для которой требуется ненулевое значение\).|  
|`_TLOSS`|Произошла полная потеря значимости.|  
|`_UNDERFLOW`|Результат слишком мал для представления.|  
  
## См. также  
 [\_matherr](../c-runtime-library/reference/matherr.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)