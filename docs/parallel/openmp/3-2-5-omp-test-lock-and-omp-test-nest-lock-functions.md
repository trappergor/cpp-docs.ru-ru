---
title: 3.2.5 функции omp_test_lock и omp_test_nest_lock функции | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5349134bf92f407d4b65df9b92e3eebe87c097c1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426150"
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