---
title: 3.1.3 функция omp_get_max_threads | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c439dc0203fa3435c62e9669da40b5b092556492
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400826"
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