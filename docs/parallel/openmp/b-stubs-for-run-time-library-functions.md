---
title: Б. Заглушки для функции библиотеки времени выполнения | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: fdfdabe0-f678-4551-80d5-827b62354427
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1207f943560fdc6a22c62a9a8deafa213400f172
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687586"
---
# <a name="b-stubs-for-run-time-library-functions"></a>Б. Заглушки для функции библиотеки времени выполнения
Этот раздел содержит заглушки для функций библиотеки времени выполнения, определенных в OpenMP C и C++ API. Включение переноса кода на платформах, которые не поддерживают OpenMP C и C++ API предоставляются заглушки. На этих платформах OpenMP программы должны быть связаны с библиотекой, содержащей эти функции-заглушки. Функции-заглушки Предположим, что директив в программе OpenMP игнорируются. Таким образом в них моделируются последовательного семантику.  
  
> [!NOTE]
>  Блокировка переменную, которая отображается в функции блокировки должен осуществляться только с помощью этих функций. Не должна быть инициализирована или в противном случае изменения в программе пользователя. Пользователи не должна делать предположений о механизмах, используемое реализациями OpenMP C и C++ для реализации блокировки на основе схемы, используемые функциями заглушки.  
  
### <a name="code"></a>Код  
  
```  
#include <stdio.h>  
#include <stdlib.h>  
#include "omp.h"  
#ifdef __cplusplus  
extern "C" {  
#endif  
  
void omp_set_num_threads(int num_threads)  
{  
}  
int omp_get_num_threads(void)  
{  
    return 1;  
}  
int omp_get_max_threads(void)  
{  
    return 1;  
}  
int omp_get_thread_num(void)  
{  
    return 0;  
}  
int omp_get_num_procs(void)  
{  
    return 1;  
}  
void omp_set_dynamic(int dynamic_threads)  
{  
}  
int omp_get_dynamic(void)  
{  
    return 0;  
}  
int omp_in_parallel(void)  
{  
    return 0;  
}  
void omp_set_nested(int nested)  
{  
}  
int omp_get_nested(void)  
{  
    return 0;  
}  
enum {UNLOCKED = -1, INIT, LOCKED};  
void omp_init_lock(omp_lock_t *lock)  
{  
    *lock = UNLOCKED;  
}  
void omp_destroy_lock(omp_lock_t *lock)  
{  
    *lock = INIT;  
}  
void omp_set_lock(omp_lock_t *lock)  
{  
    if (*lock == UNLOCKED)   
    {  
        *lock = LOCKED;  
    }   
    else   
        if (*lock == LOCKED)   
        {  
         fprintf_s(stderr, "error: deadlock in using lock variable\n");  
         exit(1);  
        } else {  
         fprintf_s(stderr, "error: lock not initialized\n");  
         exit(1);  
        }  
}  
  
void omp_unset_lock(omp_lock_t *lock)  
{  
    if (*lock == LOCKED)   
    {  
        *lock = UNLOCKED;  
    }   
    else   
        if (*lock == UNLOCKED)   
        {  
            fprintf_s(stderr, "error: lock not set\n");  
            exit(1);  
        } else {  
            fprintf_s(stderr, "error: lock not initialized\n");  
            exit(1);  
        }  
}  
  
int omp_test_lock(omp_lock_t *lock)  
{  
    if (*lock == UNLOCKED)   
    {  
        *lock = LOCKED;  
        return 1;  
    } else if (*lock == LOCKED) {  
        return 0;  
    } else {  
        fprintf_s(stderr, "error: lock not initialized\n");  
        exit(1);  
    }  
}  
  
#ifndef OMP_NEST_LOCK_T  
typedef struct {  // This really belongs in omp.h   
    int owner;  
    int count;  
} omp_nest_lock_t;  
#endif  
enum {MASTER = 0};  
void omp_init_nest_lock(omp_nest_lock_t *lock)  
{  
    lock->owner = UNLOCKED;  
    lock->count = 0;  
}  
void omp_destroy_nest_lock(omp_nest_lock_t *lock)  
{  
    lock->owner = UNLOCKED;  
    lock->count = UNLOCKED;  
}  
  
void omp_set_nest_lock(omp_nest_lock_t *lock)  
{  
    if (lock->owner == MASTER && lock->count >= 1)   
    {  
        lock->count++;  
    } else   
        if (lock->owner == UNLOCKED && lock->count == 0)   
        {  
            lock->owner = MASTER;  
            lock->count = 1;  
        } else   
        {  
       fprintf_s(stderr, "error: lock corrupted or not initialized\n");  
         exit(1);  
    }  
}  
  
void omp_unset_nest_lock(omp_nest_lock_t *lock)  
{  
    if (lock->owner == MASTER && lock->count >= 1)   
    {  
        lock->count--;  
        if (lock->count == 0)   
        {  
            lock->owner = UNLOCKED;  
        }  
    } else   
        if (lock->owner == UNLOCKED && lock->count == 0)   
        {  
            fprintf_s(stderr, "error: lock not set\n");  
            exit(1);  
        } else   
        {  
       fprintf_s(stderr, "error: lock corrupted or not initialized\n");  
       exit(1);  
    }  
}  
  
int omp_test_nest_lock(omp_nest_lock_t *lock)  
{  
    omp_set_nest_lock(lock);  
    return lock->count;  
}  
  
double omp_get_wtime(void)  
{  
    // This function does not provide a working  
    // wallclock timer. Replace it with a version  
    // customized for the target machine.  
    return 0.0;  
}  
  
double omp_get_wtick(void)  
{  
    // This function does not provide a working  
    // clock tick function. Replace it with  
    // a version customized for the target machine.  
    return 365. * 86400.;  
}  
  
#ifdef __cplusplus  
}  
#endif  
```