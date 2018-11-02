---
title: 3.2.5 Функции omp_test_lock и omp_test_nest_lock
ms.date: 11/04/2016
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
ms.openlocfilehash: e8e03699f807f23f139075560592d8846467f2c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512756"
---
# <a name="325-omptestlock-and-omptestnestlock-functions"></a>3.2.5 Функции omp_test_lock и omp_test_nest_lock

Эти функции пытаются установить блокировку, но не блокируют выполнение потока. Он следующий:

```
#include <omp.h>
int omp_test_lock(omp_lock_t *lock);
int omp_test_nest_lock(omp_nest_lock_t *lock);
```

Аргумент должен указывать на переменную инициализированный блокировки. Эти функции пытаются установить блокировку так же, как `omp_set_lock` и `omp_set_nest_lock`, за исключением того, что они не блокируют выполнение потока.

Для простой блокировки `omp_test_lock` функция возвращает ненулевое значение, если блокировка успешно задан; в противном случае возвращается ноль.

Вкладываемых блокировок `omp_test_nest_lock` функция возвращает новый счетчик вложенности, если блокировка успешно задан; в противном случае возвращается ноль.