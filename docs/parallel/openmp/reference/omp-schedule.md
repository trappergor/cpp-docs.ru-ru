---
title: "OMP_SCHEDULE | Microsoft Docs"
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
  - "OMP_SCHEDULE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_SCHEDULE OpenMP environment variable"
ms.assetid: 2295a801-e584-4d2f-826f-7ca4c88846a6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OMP_SCHEDULE
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Изменяет расширение функциональности [schedule](../../../parallel/openmp/reference/schedule.md) если предложение  `schedule(runtime)` определяет in a  `for` OR  `parallel for` директива.  
  
## Синтаксис  
  
```  
set OMP_SCHEDULE[=type[,size]]  
```  
  
## Заметки  
 Здесь:  
  
 `size` \(необязательный параметр\)  
 Определяет размер итераций.  `size` должно быть положительным целым числом.  Значение по умолчанию \- 1, за исключением случаев, когда `type` статический.  Когда недопустимый `type` существует  `runtime`.  
  
 `type`  
 Тип расписания:  
  
-   `dynamic`  
  
-   `guided`  
  
-   `runtime`  
  
-   `static`  
  
## Заметки  
 По умолчанию в реализации Visual C\+\+ стандарта OpenMP `OMP_SCHEDULE=static,0`.  
  
 Дополнительные сведения см. в разделе [4.1 OMP\_SCHEDULE](../../../parallel/openmp/4-1-omp-schedule.md).  
  
## Пример  
 Следующая команда устанавливает OMP\_SCHEDULE переменная среды:  
  
```  
set OMP_SCHEDULE="guided,2"  
```  
  
 Следующая команда выводит текущий параметр OMP\_SCHEDULE переменная среды:  
  
```  
set OMP_SCHEDULE  
```  
  
## См. также  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)