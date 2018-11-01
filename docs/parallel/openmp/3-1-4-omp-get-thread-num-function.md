---
title: 3.1.4 Функция omp_get_thread_num
ms.date: 11/04/2016
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
ms.openlocfilehash: eca8522aeab4702be390d98faaf8920f2d732244
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480942"
---
# <a name="314-ompgetthreadnum-function"></a>3.1.4 Функция omp_get_thread_num

`omp_get_thread_num` Функция возвращает номер потока, в его команды потока, выполняющего функции. Поток номеров лежит между 0 и **omp_get_num_threads()**-1, включительно. Главный поток команды является потоком 0.

Он следующий:

```
#include <omp.h>
int omp_get_thread_num(void);
```

При вызове из последовательной регион `omp_get_thread_num` возвращает 0. Если вызывается внутри параллельной области вложенного, сериализуется, эта функция возвращает 0.

## <a name="cross-references"></a>Перекрестные ссылки:

- `omp_get_num_threads` функции, см. в разделе [раздел 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) на стр. 37.