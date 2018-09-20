---
title: 3.1.4 функция omp_get_thread_num | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a21a682c051daffde16b3d5cfc63fd2d679c4de
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444922"
---
# <a name="314-ompgetthreadnum-function"></a>3.1.4 Функция omp_get_thread_num

`omp_get_thread_num` Функция возвращает номер потока, в его команды потока, выполняющего функции. Поток номеров лежит между 0 и **omp_get_num_threads()**-1, включительно. Главный поток команды является потоком 0.

Он следующий:

```
#include <omp.h>
int omp_get_thread_num(void);
```

При вызове из последовательной регион `omp_get_thread_num` возвращает 0. Если вызывается внутри параллельной области вложенного, сериализуется, эта функция возвращает 0.

## <a name="cross-references"></a>Перекрестные ссылки:

- `omp_get_num_threads` функции, см. в разделе [раздел 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) на стр. 37.