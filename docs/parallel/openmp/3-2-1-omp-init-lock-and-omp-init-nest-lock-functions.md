---
title: 3.2.1 omp_init_lock and omp_init_nest_lock функции | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f14e182e6c981cd5de7a4cf92d8c285a4b49c66
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="321-ompinitlock-and-ompinitnestlock-functions"></a>3.2.1 Функции omp_init_lock and omp_init_nest_lock
Эти функции используются только инициализации блокировки. Каждая функция инициализирует блокировки, связанный с параметром *блокировки* для использования при последующих вызовах. Он следующий:  
  
```  
#include <omp.h>  
void omp_init_lock(omp_lock_t *lock);  
void omp_init_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Начальное состояние разблокирован (то есть, ни один поток владеет блокировкой). Которая блокировки вложенности исходное значение счетчика равно нулю. Он не соответствует требованиям для вызова одной из этих подпрограмм блокировку переменной, которая уже была инициализирована.