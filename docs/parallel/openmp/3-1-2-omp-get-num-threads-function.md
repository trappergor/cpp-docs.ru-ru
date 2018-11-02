---
title: 3.1.2 Функция omp_get_num_threads
ms.date: 11/04/2016
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
ms.openlocfilehash: 587b49f70896bcfe8c1a805a4ebb13a11e9bb7d0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465251"
---
# <a name="312-ompgetnumthreads-function"></a>3.1.2 Функция omp_get_num_threads

**Omp_get_num_threads** функция возвращает число потоков в настоящее время в команде выполнения параллельной области, из которого он вызывается. Он следующий:

```
#include <omp.h>
int omp_get_num_threads(void);
```

**Num_threads** предложение, **omp_set_num_threads** функции и **OMP_NUM_THREADS** число потоков в группе управления переменной среды.

Если число потоков не было явно задано пользователем, значение по умолчанию определяется реализацией. Эта функция выполняет привязку к ближайший включающий **параллельных** директива. Если вызывается из последовательной часть программы, или из вложенных параллельных регион, который сериализуется, эта функция возвращает 1.

## <a name="cross-references"></a>Перекрестные ссылки:

- **OMP_NUM_THREADS** переменной, см. в разделе среды [разделе 4.2](../../parallel/openmp/4-2-omp-num-threads.md) на стр. 48.

- **num_threads** предложение, см. в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице "8".

- **Параллельные** конструкцию, см. в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице "8".