---
title: "omp_set_nested | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "omp_set_nested"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "omp_set_nested OpenMP function"
ms.assetid: fa1cb08c-7b8b-42c9-8654-2c33dcffb5b6
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# omp_set_nested
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Разрешает вложенные параллелизм.  
  
## Синтаксис  
  
```  
void omp_set_nested(  
   int val  
);  
```  
  
## Заметки  
 Здесь:  
  
 `val`  
 Если значение ненулевое, включает вложенные параллелизм.  Если значение равно нулю, отключение вложенных параллелизм.  
  
## Заметки  
 Параллелизм вложенные OMP, который можно включить с `omp_set_nested`либо, присвоив  [OMP\_NESTED](../../../parallel/openmp/reference/omp-nested.md) переменная среды.  
  
 Параметр `omp_set_nested` переопределяет параметр  `OMP_NESTED` переменная среды.  
  
 При включении переменная среды выполнения может нарушить в противном случае \- a программы, поскольку количество потоков растет экспоненциально при вложении параллельные области.  Например, функция создаст recurses 6 с количеством потоков OMP присвойте значение 4 необходимо 4.096 \(4 в степень 6\) потоков в целом производительность приложения ухудшат если число потоков превышает число процессоров.  Одно исключение из этого были бы связанными приложениями ВВОДА\-ВЫВОДА.  
  
 Используйте [omp\_get\_nested](../../../parallel/openmp/reference/omp-get-nested.md) отобразить текущий параметр  `omp_set_nested`.  
  
 Дополнительные сведения см. в разделе [3.1.9 omp\_set\_nested Function](../../../parallel/openmp/3-1-9-omp-set-nested-function.md).  
  
## Пример  
  
```  
// omp_set_nested.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    omp_set_nested(1);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_nested( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_nested( ));  
        }  
}  
```  
  
  **1**  
**1**   
## См. также  
 [Functions](../../../parallel/openmp/reference/openmp-functions.md)