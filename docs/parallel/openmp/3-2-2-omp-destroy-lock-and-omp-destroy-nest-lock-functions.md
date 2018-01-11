---
title: "3.2.2 функции omp_destroy_lock и omp_destroy_nest_lock функции | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5d0b91fd311581235a893a0b3f4f383e724f9aa6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="322-ompdestroylock-and-ompdestroynestlock-functions"></a>3.2.2 Функции omp_destroy_lock и omp_destroy_nest_lock
Эти функции убедитесь, что указывает на блокировку переменной *блокировки* не инициализирован. Он следующий:  
  
```  
#include <omp.h>  
void omp_destroy_lock(omp_lock_t *lock);  
void omp_destroy_nest_lock(omp_nest_lock_t *lock);  
```  
  
 Он не соответствует требованиям для вызова одной из этих подпрограмм блокировку переменной, которая является не инициализирован или разблокировать.