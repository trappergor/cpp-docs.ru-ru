---
title: "Константы кучи | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_HEAPBADPTR"
  - "_HEAPEMPTY"
  - "_HEAPBADBEGIN"
  - "_HEAPOK"
  - "_HEAPBADNODE"
  - "_HEAPEND"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_HEAPBADBEGIN - константы"
  - "_HEAPBADNODE - константы"
  - "_HEAPBADPTR - константы"
  - "_HEAPEMPTY - константы"
  - "_HEAPEND - константы"
  - "_HEAPOK - константы"
  - "heap - константы"
  - "HEAPBADBEGIN - константы"
  - "HEAPBADNODE - константы"
  - "HEAPBADPTR - константы"
  - "HEAPEMPTY - константы"
  - "HEAPEND - константы"
  - "HEAPOK - константы"
ms.assetid: 3f751bb9-2dc4-486f-b5f5-9061c96d3754
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Константы кучи
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <malloc.h>  
  
```  
  
## Заметки  
 Эти константы предоставляют возвращаемое значение, отображающее состояние кучи.  
  
|Константа|Значение|  
|---------------|--------------|  
|`_HEAPBADBEGIN`|Начальные сведения о заголовке не найдены или недопустимы.|  
|`_HEAPBADNODE`|Недопустимый узел был найден или куча была повреждена.|  
|`_HEAPBADPTR`|Поле **\_pentry** структуры **\_HEAPINFO** не содержит допустимого указателя на кучу \(только для процедуры `_heapwalk`\).|  
|`_HEAPEMPTY`|Куча не инициализирована.|  
|`_HEAPEND`|Конец кучи успешно достигнут \(только для процедуры `_heapwalk`\).|  
|`_HEAPOK`|Куча не согласована \(только для процедур `_heapset` и `_heapchk`\).  Без ошибок до сих пор; структура **\_HEAPINFO** содержит сведения о следующей записи \(только для процедуры `_heapwalk`\).|  
  
## См. также  
 [\_heapchk](../c-runtime-library/reference/heapchk.md)   
 [\_heapset](../c-runtime-library/heapset.md)   
 [\_heapwalk](../Topic/_heapwalk.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)