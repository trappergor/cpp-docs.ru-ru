---
title: 3.2.4 omp_unset_lock и omp_unset_nest_lock функции | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f480a75efff737356c1477593e182537ae73a8c8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="324-ompunsetlock-and-ompunsetnestlock-functions"></a>3.2.4 Функции omp_unset_lock и omp_unset_nest_lock
Эти функции предоставляют средства по освобождению владение блокировки. Он следующий:  
  
```  
#include <omp.h>  
void omp_unset_lock(omp_lock_t *lock);  
void omp_unset_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Аргумент для каждого из этих функций должен указывать на переменную инициализированный блокировки, принадлежащий потоку, выполнение функции. Если поток не является владельцем блокировки, поведение не определено.  
  
 Простые блокировки `omp_unset_lock` функция освобождает поток, выполняющий функции с владельцем блокировки.  
  
 Которая блокировки `omp_unset_nest_lock` функция уменьшает значение счетчика вложенности, а также версии поток, функция с владельцем блокировки, если счетчик равен нулю.