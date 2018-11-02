---
title: A.15   Определение количества используемых потоков
ms.date: 11/04/2016
ms.assetid: 026bb59a-f668-40db-a7cb-69a1bae83d2d
ms.openlocfilehash: bd5e897eeab35ec73c061d2ae02a4b85772e1255
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525853"
---
# <a name="a15---determining-the-number-of-threads-used"></a>A.15   Определение количества используемых потоков

Рассмотрим следующий пример неверные (для [раздел 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) на стр. 37):

```
np = omp_get_num_threads(); // misplaced
#pragma omp parallel for schedule(static)
    for (i=0; i<np; i++)
        work(i);
```

`omp_get_num_threads()` Вызов возвращает значение 1 в последовательной раздела кода, поэтому *np* всегда будет равно 1 в предыдущем примере. Чтобы определить количество потоков, которые будут развернуты для параллельной области, внутри параллельной области должен быть вызов.

Приведенный ниже показано, как переписывать этой программы, не включая запрос для потоков:

```
#pragma omp parallel private(i)
{
    i = omp_get_thread_num();
    work(i);
}
```