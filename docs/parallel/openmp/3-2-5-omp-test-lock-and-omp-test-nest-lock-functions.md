---
title: "3.2.5 omp_test_lock и omp_test_nest_lock функции | Документы Microsoft"
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
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8fcdacdbb38a9bb27e35ada74aa2139be10c6797
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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