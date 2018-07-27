---
title: Указания фиксированного числа потоков а.11 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 1d06b142-4c35-44b8-994b-20f2aed5462b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71d09c470b76b61c6737566f7833334aeec6c63a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686543"
---
# <a name="a11---specifying-a-fixed-number-of-threads"></a>A.11   Задание фиксированного количества потоков
Некоторые программы используют фиксированное, предопределенное число потоков, подлежащих выполнению правильно.  Так как значение по умолчанию динамическую настройку число потоков зависит от реализации, такие программы можно отключить возможность динамического потоков и задайте число потоков явным образом для обеспечения переносимости. В следующем примере показано, как это сделать с помощью `omp_set_dynamic` ([раздел 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на странице 39), и `omp_set_num_threads` ([раздел 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) на стр.):  
  
```  
omp_set_dynamic(0);  
omp_set_num_threads(16);  
#pragma omp parallel shared(x, npoints) private(iam, ipoints)  
{  
    if (omp_get_num_threads() != 16)   
      abort();  
    iam = omp_get_thread_num();  
    ipoints = npoints/16;  
    do_by_16(x, iam, ipoints);  
}  
```  
  
 В этом примере программа выполняется правильно только в том случае, если он выполняется по 16 потоков. Если реализация не поддерживает 16 потоков, поведение в этом примере определяется реализацией.  
  
 Обратите внимание, что число потоков, выполняемых параллельной области остается постоянным во время параллельной области, независимо от того, динамический параметр потоков. Механизм динамической потоков определяет число потоков, используемых в начале параллельной области и отслеживает постоянным в течение области.