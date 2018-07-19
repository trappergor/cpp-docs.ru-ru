---
title: 3.2.5 omp_test_lock и omp_test_nest_lock функции | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5023f0b089d76e92be886f4917905f57dda7a018
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686231"
---
# <a name="325-omptestlock-and-omptestnestlock-functions"></a>3.2.5 Функции omp_test_lock и omp_test_nest_lock
Эти функции пытается установить блокировку, а не блокируют выполнение потока. Он следующий:  
  
```  
#include <omp.h>  
int omp_test_lock(omp_lock_t *lock);  
int omp_test_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Аргумент должен указывать на переменную инициализированный блокировки. Попытка установить блокировку так же, как эти функции `omp_set_lock` и `omp_set_nest_lock`, за исключением того, что они не блокировали выполнение потока.  
  
 Простые блокировки `omp_test_lock` функция возвращает ненулевое значение, если блокировка успешно установлена; в противном случае возвращается ноль.  
  
 Которая блокировки `omp_test_nest_lock` функция возвращает количество новых вложенности, если блокировка успешно установлена; в противном случае возвращается ноль.