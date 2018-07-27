---
title: 3.2.3 omp_set_lock и omp_set_nest_lock функции | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba24e923051eb887db2a81c1d9765d31a4ef7b24
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689718"
---
# <a name="323-ompsetlock-and-ompsetnestlock-functions"></a>3.2.3 Функции omp_set_lock и omp_set_nest_lock
Каждая из этих функций блокирует поток, выполняющий функции, пока указанная блокировка имеет доступные и устанавливает блокировку. Простая блокировка доступен в том случае, если он не заблокирован. Блокировку, которая доступна, если разблокирован или если он уже принадлежит поток, выполняющий функции. Он следующий:  
  
```  
#include <omp.h>  
void omp_set_lock(omp_lock_t *lock);  
void omp_set_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Простые блокировки аргумент `omp_set_lock` функции должен указывать на переменную инициализированный блокировки. Поток, выполняющий функции предоставляется владельцем блокировки.  
  
 Которая блокировки аргумент `omp_set_nest_lock` функции должен указывать на переменную инициализированный блокировки. Вложенности увеличивается, и предоставляется потоком, или же сохраняет владельца блокировки.