---
title: "3.2.4 omp_unset_lock и omp_unset_nest_lock функции | Документы Microsoft"
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
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dc71c6c31a1d93b6e9c9cce2cd4f7830502a1a2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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