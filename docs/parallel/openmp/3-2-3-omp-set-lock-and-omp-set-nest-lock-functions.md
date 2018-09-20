---
title: 3.2.3 функции omp_set_lock и omp_set_nest_lock функции | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 792b95baef2821bb693d9a90fc228d2b0c508e1f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420365"
---
# <a name="323-ompsetlock-and-ompsetnestlock-functions"></a>3.2.3 Функции omp_set_lock и omp_set_nest_lock

Каждая из этих функций блокирует поток, выполняющий функции, пока указанная блокировка доступна, а затем устанавливает блокировку. Простой блокировки доступен в том случае, если она не закреплена. Вкладываемых блокировка доступна, если она не закреплена или если он уже принадлежит поток, выполняющий функции. Он следующий:

```
#include <omp.h>
void omp_set_lock(omp_lock_t *lock);
void omp_set_nest_lock(omp_nest_lock_t *lock);
```

Для простой блокировки, аргумент `omp_set_lock` функции должен указывать на переменную инициализированный блокировки. Поток, выполняющий функции предоставляется владельцем блокировки.

Вкладываемых блокировок, аргумент `omp_set_nest_lock` функции должен указывать на переменную инициализированный блокировки. Вложения увеличивается, и предоставляется потоком, или же сохраняет, владение блокировки.