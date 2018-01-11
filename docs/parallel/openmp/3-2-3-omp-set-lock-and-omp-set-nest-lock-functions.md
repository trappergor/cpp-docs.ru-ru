---
title: "3.2.3 omp_set_lock и omp_set_nest_lock функции | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e709e43a0b32b68bc34c4e76e8680ae371e30670
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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