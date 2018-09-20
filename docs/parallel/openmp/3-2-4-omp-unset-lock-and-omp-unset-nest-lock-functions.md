---
title: 3.2.4 функции omp_unset_lock и omp_unset_nest_lock функции | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 426ac0a5ff974e486f70eed2965fdc27d5acc941
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419117"
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