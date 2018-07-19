---
title: Использование блокировок A.16 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 873bf32b-6cfe-4ce1-b994-bef80b50f399
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db55a8e562e0b1ae72038128a035d2cdabcd3e86
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695906"
---
# <a name="a16---using-locks"></a>A.16   Использование блокировок
В следующем примере (для [разделе 3.2](../../parallel/openmp/3-2-lock-functions.md) на странице 41) Обратите внимание, что тип должен быть аргументом для функции блокировки `omp_lock_t`, и что нет необходимости в его очистка.  Функции блокировки вызывают потоков простаивает во время ожидания для записи на первый критический раздел, но для выполнения других операций во время ожидания операции на второй.  `omp_set_lock` Блоки функции, но `omp_test_lock` функция не имеет, допускающей работу в skip() должна быть выполнена.  
  
## <a name="example"></a>Пример  
  
### <a name="code"></a>Код  
  
```  
// omp_using_locks.c  
// compile with: /openmp /c  
#include <stdio.h>  
#include <omp.h>  
  
void work(int);  
void skip(int);  
  
int main() {  
   omp_lock_t lck;  
   int id;  
  
   omp_init_lock(&lck);  
   #pragma omp parallel shared(lck) private(id)  
   {  
      id = omp_get_thread_num();  
  
      omp_set_lock(&lck);  
      printf_s("My thread id is %d.\n", id);  
  
      // only one thread at a time can execute this printf  
      omp_unset_lock(&lck);  
  
      while (! omp_test_lock(&lck)) {  
         skip(id);   // we do not yet have the lock,  
                     // so we must do something else   
      }  
      work(id);     // we now have the lock  
                    // and can do the work   
      omp_unset_lock(&lck);  
   }  
   omp_destroy_lock(&lck);  
}  
```