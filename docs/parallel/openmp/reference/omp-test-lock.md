---
title: функции omp_test_lock | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_test_lock
dev_langs:
- C++
helpviewer_keywords:
- omp_test_lock OpenMP function
ms.assetid: 314ca85e-0749-4c16-800f-b0f36fed256d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c34edd258c087f70bc9bb0b732cfd7ca192c791c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106107"
---
# <a name="omptestlock"></a>omp_test_lock
Пытается установить блокировку, но не блокирует выполнение потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int omp_test_lock(  
   omp_lock_t *lock  
);  
```  
  
### <a name="parameters"></a>Параметры
  
*lock*<br/>
Переменная типа [omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md) , инициализированный с [функции omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md).  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [3.2.5 функции omp_test_lock и omp_test_nest_lock функции](../../../parallel/openmp/3-2-5-omp-test-lock-and-omp-test-nest-lock-functions.md).  
  
## <a name="example"></a>Пример  
  
```  
// omp_test_lock.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
omp_lock_t simple_lock;                   
  
int main() {  
    omp_init_lock(&simple_lock);  
  
    #pragma omp parallel num_threads(4)  
    {  
        int tid = omp_get_thread_num();  
  
        while (!omp_test_lock(&simple_lock))  
            printf_s("Thread %d - failed to acquire simple_lock\n",  
                     tid);  
  
        printf_s("Thread %d - acquired simple_lock\n", tid);  
  
        printf_s("Thread %d - released simple_lock\n", tid);  
        omp_unset_lock(&simple_lock);  
    }  
  
    omp_destroy_lock(&simple_lock);  
}  
```  
  
```Output  
Thread 1 - acquired simple_lock  
Thread 1 - released simple_lock  
Thread 0 - failed to acquire simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 0 - failed to acquire simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 2 - acquired simple_lock  
Thread 0 - failed to acquire simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 0 - failed to acquire simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 2 - released simple_lock  
Thread 0 - failed to acquire simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 0 - acquired simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 0 - released simple_lock  
Thread 3 - failed to acquire simple_lock  
Thread 3 - acquired simple_lock  
Thread 3 - released simple_lock  
```  
  
## <a name="see-also"></a>См. также  
 [Функции](../../../parallel/openmp/reference/openmp-functions.md)