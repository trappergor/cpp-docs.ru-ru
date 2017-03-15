---
title: "A.25   Examples of the copyprivate Data Attribute Clause | Microsoft Docs"
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
ms.assetid: 7b1cb6a5-5691-4b95-b3ac-d7543ede6405
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# A.25   Examples of the copyprivate Data Attribute Clause
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Пример 1.** `copyprivate` предложение \([Раздел 2.7.2.8](../Topic/2.7.2.8%20copyprivate.md) на странице 32\) может использоваться для вещать значения приобретенные одним потоком непосредственно ко всем экземплярам закрытых переменных в других потоках.  
  
```  
float x, y;  
#pragma omp threadprivate(x, y)  
  
void init( )   
{  
    float a;  
    float b;  
  
    #pragma omp single copyprivate(a,b,x,y)  
    {  
        get_values(a,b,x,y);  
    }  
  
    use_values(a, b, x, y);  
}  
```  
  
 Если подпрограмма *init* вызывает метод с серийной области, его функциональности не влияет на присутствием директив.  После вызова *get\_values* подпрограмма не будет выполнена одним потоком, поток оставляет конструкция до закрытых объектов, обозначенных by *a*" *в*" *x*и *y* во всех потоках станьте указанными с считанные значения.  
  
 **Пример 2.** В отличие от предыдущего примера, предположим, что должно выполняться чтение указанным потоком, сообщает главный поток.  В этом случае `copyprivate` предложение нельзя использовать для широковещательной напрямую, но его можно использовать для обеспечения доступа к временному общий объект.  
  
```  
float read_next( )   
{  
    float * tmp;  
    float return_val;  
  
    #pragma omp single copyprivate(tmp)  
    {  
        tmp = (float *) malloc(sizeof(float));  
    }  
  
    #pragma omp master  
    {  
        get_float( tmp );  
    }  
  
    #pragma omp barrier  
    return_val = *tmp;  
    #pragma omp barrier  
  
    #pragma omp single  
    {  
       free(tmp);  
    }  
  
    return return_val;  
}  
```  
  
 **Пример 3.** Полагает, что количество объектов блокировки необходимости в параллельной области не легко может быть определено до его вставки.  `copyprivate` предложение может быть использован для доступа к объектам совмещаемой блокировки, выбранные в этой параллельной области.  
  
```  
#include <omp.h>  
  
omp_lock_t *new_lock()  
{  
    omp_lock_t *lock_ptr;  
  
    #pragma omp single copyprivate(lock_ptr)  
    {  
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));  
        omp_init_lock( lock_ptr );  
    }  
  
    return lock_ptr;  
}  
```