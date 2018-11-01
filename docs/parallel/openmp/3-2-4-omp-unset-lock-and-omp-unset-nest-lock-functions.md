---
title: 3.2.4 Функции omp_unset_lock и omp_unset_nest_lock
ms.date: 11/04/2016
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
ms.openlocfilehash: b0764e3590f8edb3a3e783d9b5493a64be154401
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607874"
---
# <a name="324-ompunsetlock-and-ompunsetnestlock-functions"></a>3.2.4 Функции omp_unset_lock и omp_unset_nest_lock

Эти функции предоставляют средства по освобождению владельца блокировки. Он следующий:

```
#include <omp.h>
void omp_unset_lock(omp_lock_t *lock);
void omp_unset_nest_lock(omp_nest_lock_t *lock);
```

Аргумент для каждой из этих функций должен указывать на переменную инициализированный блокировки, принадлежащий потоку выполнения функции. Если поток не владеет, поведение не определено.

Для простой блокировки `omp_unset_lock` функция освобождает поток, выполняющий функции из владельца блокировки.

Вкладываемых блокировок `omp_unset_nest_lock` уменьшает число вложенности и функции выпусков поток, выполняющий функцию с владельцем блокировки, если счетчик принял значение ноль.