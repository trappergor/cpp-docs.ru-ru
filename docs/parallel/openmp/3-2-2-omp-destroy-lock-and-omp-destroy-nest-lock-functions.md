---
title: 3.2.2 функции omp_destroy_lock и omp_destroy_nest_lock функции | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b7b762614e406e5fb4497ec901ad8f65dae15a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433880"
---
# <a name="322-ompdestroylock-and-ompdestroynestlock-functions"></a>3.2.2 Функции omp_destroy_lock и omp_destroy_nest_lock

Эти функции убедитесь, что указывает на переменную блокировки *блокировки* не инициализирована. Он следующий:

```
#include <omp.h>
void omp_destroy_lock(omp_lock_t *lock);
void omp_destroy_nest_lock(omp_nest_lock_t *lock);
```

Он не соответствует требованиям, если ни один из этих подпрограмм с переменной блокировку, не инициализирована или разблокировать.