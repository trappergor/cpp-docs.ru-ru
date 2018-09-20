---
title: 3.2.1 функции omp_init_lock и omp_init_nest_lock функции | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4303eb3ccfcb1c449022a4be32f94b9f91e6e80c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387007"
---
# <a name="321-ompinitlock-and-ompinitnestlock-functions"></a>3.2.1 Функции omp_init_lock and omp_init_nest_lock

Эти функции представляют собой единственный способ инициализации блокировки. Каждая функция инициализирует блокировкой, связанной с параметром *блокировки* для использования в последующих вызовах. Он следующий:

```
#include <omp.h>
void omp_init_lock(omp_lock_t *lock);
void omp_init_nest_lock(omp_nest_lock_t *lock);
```

Начальное состояние разблокируется (то есть, ни один поток не владеет блокировкой). Вкладываемых блокировок исходное количество вложенности равен нулю. Он не соответствует требованиям, если ни один из этих подпрограмм с переменной блокировки, который уже был инициализирован.