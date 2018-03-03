---
title: "Примеры A.25 copyprivate предложение атрибута данных | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 7b1cb6a5-5691-4b95-b3ac-d7543ede6405
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7cdf7598e00bab72966fe79454567b0a59dcbaae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="a25---examples-of-the-copyprivate-data-attribute-clause"></a>A.25   Примеры предложения атрибута данных copyprivate
**Пример 1:** `copyprivate` предложение ([раздел 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) на странице 32) может использоваться для передачи значений, получена из одного потока, непосредственно ко всем экземплярам закрытые переменные в других потоков.  
  
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
  
 Если сопоставление *init* вызывается из последовательного региона, его поведение не влияет на наличие директивы. После вызова *get_values* процедура выполнена одним потоком, ни один поток покидает конструкция до закрытых объектов, обозначенный *a*, *b*, *x*, и *y* во всех потоках становятся определили со значениями, считанными.  
  
 **Пример 2:** в отличие от предыдущего примера, предположим, read должна выполняться в определенном потоке, например главного потока. В этом случае `copyprivate` предложения не может использоваться для выполнения вещания непосредственно, но он может использоваться для предоставления доступа к общей временный объект.  
  
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
  
 **Пример 3.** Предположим, что количество блокировок объектов, необходимых в параллельной области невозможно легко определить до его ввода. `copyprivate` Предложение может использоваться для предоставления доступа к совмещаемой блокировки объектов, размещенных в этой параллельной области.  
  
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