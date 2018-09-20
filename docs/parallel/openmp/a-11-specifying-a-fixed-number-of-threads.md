---
title: A.11 задание фиксированного количества потоков | Документация Майкрософт
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
ms.openlocfilehash: 892140425dc9f7083c606fce3ffe671a107a65ca
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422991"
---
# <a name="a11---specifying-a-fixed-number-of-threads"></a>A.11   Задание фиксированного количества потоков

Некоторые программы используют фиксированное, предопределенное число потоков для выполнения правильно.  Поскольку динамическую настройку количество потоков по умолчанию, определяемое реализацией, таких программ можно отключить возможность динамического потоков и задайте число потоков, явным образом для обеспечения переносимости. В следующем примере показано, как это сделать с помощью `omp_set_dynamic` ([разделе 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на стр. 39), и `omp_set_num_threads` ([разделе 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) на странице 36):

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

В этом примере программа работает правильно только в том случае, если он выполняется по 16 потоков. Если реализация не поддерживает 16 потоков, поведение в этом примере определяется реализацией.

Обратите внимание, что количество потоков, выполняющих параллельной области остается постоянным во время параллельной области, независимо от параметра динамические потоки. Механизм динамических потоков определяет число потоков, используемых в начале параллельной области и поддерживает постоянное до конца области.