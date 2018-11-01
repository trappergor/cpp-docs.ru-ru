---
title: 3.1.3 Функция omp_get_max_threads
ms.date: 11/04/2016
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
ms.openlocfilehash: 3f954b5ad75b4bdb4a74323f2ab4e819850269ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546596"
---
# <a name="313-ompgetmaxthreads-function"></a>3.1.3 Функция omp_get_max_threads

**Omp_get_max_threads** функция возвращает целое число, которое гарантированно будет по крайней мере число потоков, которые используются для формирования команды, если параллельной области без **num_threads** предложение пришлось столкнуться на этом этапе в коде. Он следующий:

```
#include <omp.h>
int omp_get_max_threads(void);
```

Следующие выражает нижняя граница диапазона на значении **omp_get_max_threads**:

```

threads-used-for-next-team
<= omp_get_max_threads

```

Обратите внимание, что если последующие параллельной области использует **num_threads** предложение, чтобы запросить определенное количество потоков, гарантии на нижнюю границу результат **omp_get_max_threads** не содержит много.

**Omp_get_max_threads** возвращаемое значение функции можно использовать для динамического выделения достаточный объем хранилища для всех потоков в группе, сформированный в последующих область параллельной обработки.

## <a name="cross-references"></a>Перекрестные ссылки:

- **omp_get_num_threads** функции, см. в разделе [раздел 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) на стр. 37.

- **omp_set_num_threads** функции, см. в разделе [разделе 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) на странице 36.

- **omp_set_dynamic** функции, см. в разделе [разделе 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на стр. 39.

- **num_threads** предложение, см. в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице "8".