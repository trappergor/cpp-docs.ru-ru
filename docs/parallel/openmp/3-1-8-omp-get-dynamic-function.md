---
title: 3.1.8 Функция omp_get_dynamic
ms.date: 11/04/2016
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
ms.openlocfilehash: d9476894e5aff4cc7bb9c67fbbeb14d185b65f5e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566430"
---
# <a name="318-ompgetdynamic-function"></a>3.1.8 Функция omp_get_dynamic

**Omp_get_dynamic** функция возвращает ненулевое значение, если динамическую настройку потоков и в противном случае возвращает 0. Он следующий:

```
#include <omp.h>
int omp_get_dynamic(void);
```

Если реализация не использует динамическую настройку число потоков, эта функция всегда возвращает 0.

## <a name="cross-references"></a>Перекрестные ссылки:

- Описание динамического потока коррекции, см. в разделе [разделе 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на стр. 39.