---
title: "3.3.1 omp_get_wtime Function | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.3.1 omp_get_wtime Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`omp_get_wtime` функция возвращает значение с плавающей запятой двойной точности, эквивалентное истеченному реальное время в секундах с момента некоторые "создаст в прошлом".  Фактическое "время" в прошлом произвольно, но гарантирует, какие изменения во время выполнения программы приложения.  Формат следующий:  
  
```  
#include <omp.h>  
double omp_get_wtime(void);  
```  
  
 Предвидится, что функция будет использоваться для измерения затраченные раз, как показано в следующем примере:  
  
```  
double start;  
double end;  
start = omp_get_wtime();  
... work to be timed ...  
end = omp_get_wtime();  
printf_s("Work took %f sec. time.\n", end-start);  
```  
  
 Возвращаемые значения времени "создаст в\-поток", что значено, что они должны иметь глобально последовательно через все потоки, участвующих в приложении.