---
title: A.3   Использование параллельных регионов
ms.date: 11/04/2016
ms.assetid: 575216a1-960a-47f7-9c82-7f660291fcfe
ms.openlocfilehash: 573c4f7c47c90bc6d567c4640360aa6abee5a48c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458998"
---
# <a name="a3---using-parallel-regions"></a>A.3   Использование параллельных регионов

`parallel` Директива ([разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице "8") можно использовать в крупных фрагментов данных параллельных программ. В следующем примере каждый поток в параллельной области определяет, какая часть глобального массива `x` для работы, в зависимости от числа потоков:

```
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)
{
    iam = omp_get_thread_num();
    np =  omp_get_num_threads();
    ipoints = npoints / np;
    subdomain(x, iam, ipoints);
}
```