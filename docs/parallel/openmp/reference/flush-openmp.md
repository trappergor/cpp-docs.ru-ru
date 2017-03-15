---
title: "flush (OpenMP) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Flush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "flush OpenMP directive"
ms.assetid: 150ca46e-d4f7-4423-b0a4-838df40aeb67
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# flush (OpenMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Указывает, что все потоки имеют одинаковое представление в памяти для всех общих объектов.  
  
## Синтаксис  
  
```  
#pragma omp flush [(var)]  
```  
  
## Заметки  
 Здесь:  
  
 `var` \(необязательный параметр\)  
 Список переменных с разделителями\-запятыми, представляющие объекты, которые нужно синхронизировать.  If `var` не указан, вся память очищается.  
  
## Заметки  
 **flush** директива не поддерживает никаких предложений OpenMP.  
  
 Дополнительные сведения см. в разделе [2.6.5 flush Directive](../Topic/2.6.5%20flush%20Directive.md).  
  
## Пример  
  
```  
// omp_flush.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
void read(int *data) {  
   printf_s("read data\n");  
   *data = 1;  
}  
  
void process(int *data) {  
   printf_s("process data\n");  
   (*data)++;  
}  
  
int main() {  
   int data;  
   int flag;  
  
   flag = 0;  
  
   #pragma omp parallel sections num_threads(2)  
   {  
      #pragma omp section  
      {  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         read(&data);  
         #pragma omp flush(data)  
         flag = 1;  
         #pragma omp flush(flag)  
         // Do more work.  
      }  
  
      #pragma omp section   
      {  
         while (!flag) {  
            #pragma omp flush(flag)  
         }  
         #pragma omp flush(data)  
  
         printf_s("Thread %d: ", omp_get_thread_num( ));  
         process(&data);  
         printf_s("data = %d\n", data);  
      }  
   }  
}  
```  
  
  **Поток 0. чтение данных**  
**Поток 1. процесс данных**  
**данные \= 2**   
## См. также  
 [Directives](../../../parallel/openmp/reference/openmp-directives.md)