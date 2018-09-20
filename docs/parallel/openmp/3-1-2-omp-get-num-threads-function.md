---
title: 3.1.2 функция omp_get_num_threads | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 512c09b0cf71a7fd9c7438b6f9cceb9f16126718
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424988"
---
# <a name="312-ompgetnumthreads-function"></a>3.1.2 Функция omp_get_num_threads

**Omp_get_num_threads** функция возвращает число потоков в настоящее время в команде выполнения параллельной области, из которого он вызывается. Он следующий:

```
#include <omp.h>
int omp_get_num_threads(void);
```

**Num_threads** предложение, **omp_set_num_threads** функции и **OMP_NUM_THREADS** число потоков в группе управления переменной среды.

Если число потоков не было явно задано пользователем, значение по умолчанию определяется реализацией. Эта функция выполняет привязку к ближайший включающий **параллельных** директива. Если вызывается из последовательной часть программы, или из вложенных параллельных регион, который сериализуется, эта функция возвращает 1.

## <a name="cross-references"></a>Перекрестные ссылки:

- **OMP_NUM_THREADS** переменной, см. в разделе среды [разделе 4.2](../../parallel/openmp/4-2-omp-num-threads.md) на стр. 48.

- **num_threads** предложение, см. в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице "8".

- **Параллельные** конструкцию, см. в разделе [разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице "8".