---
title: 3.3.1 функция omp_get_wtime | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ec022e9c7e27c848ef535481993dd18dc45f695
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430778"
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