---
title: 3.2.2 Функции omp_destroy_lock и omp_destroy_nest_lock
ms.date: 11/04/2016
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
ms.openlocfilehash: 02f739ab2834db7eca9b051e6659644c39b51e84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666210"
---
# <a name="322-ompdestroylock-and-ompdestroynestlock-functions"></a>3.2.2 Функции omp_destroy_lock и omp_destroy_nest_lock

Эти функции убедитесь, что указывает на переменную блокировки *блокировки* не инициализирована. Он следующий:

```
#include <omp.h>
void omp_destroy_lock(omp_lock_t *lock);
void omp_destroy_nest_lock(omp_nest_lock_t *lock);
```

Он не соответствует требованиям, если ни один из этих подпрограмм с переменной блокировку, не инициализирована или разблокировать.