---
title: 3.3.1 Функция omp_get_wtime
ms.date: 11/04/2016
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
ms.openlocfilehash: 544a1bc9a613a2888cb7c5e68e54fdfae1b1c333
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460571"
---
# <a name="331-ompgetwtime-function"></a>3.3.1 Функция omp_get_wtime

`omp_get_wtime` Функция возвращает значение с плавающей запятой двойной точности, равным затраченного реального времени в секундах с момента некоторые «времени в прошлом».  Фактическое «время в прошлом» может быть произвольным, но оно не меняется во время исполнения программы приложения. Он следующий:

```
#include <omp.h>
double omp_get_wtime(void);
```

Предполагается, что функция будет использоваться для измерения времени, затраченного на, как показано в следующем примере:

```
double start;
double end;
start = omp_get_wtime();
... work to be timed ...
end = omp_get_wtime();
printf_s("Work took %f sec. time.\n", end-start);
```

Время, возвращаемое API являются «по потокам раз», что означало, что они не обязаны быть глобально согласованным на всех потоков, участвующих в приложении.