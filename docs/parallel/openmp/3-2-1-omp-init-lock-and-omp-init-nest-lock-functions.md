---
title: 3.2.1 Функции omp_init_lock and omp_init_nest_lock
ms.date: 11/04/2016
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
ms.openlocfilehash: 2d15aacb5e6743d18150fb45bea85b7ca22a401f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472784"
---
# <a name="321-ompinitlock-and-ompinitnestlock-functions"></a>3.2.1 Функции omp_init_lock and omp_init_nest_lock

Эти функции представляют собой единственный способ инициализации блокировки. Каждая функция инициализирует блокировкой, связанной с параметром *блокировки* для использования в последующих вызовах. Он следующий:

```
#include <omp.h>
void omp_init_lock(omp_lock_t *lock);
void omp_init_nest_lock(omp_nest_lock_t *lock);
```

Начальное состояние разблокируется (то есть, ни один поток не владеет блокировкой). Вкладываемых блокировок исходное количество вложенности равен нулю. Он не соответствует требованиям, если ни один из этих подпрограмм с переменной блокировки, который уже был инициализирован.