---
title: 3.1.10 Функция omp_get_nested
ms.date: 11/04/2016
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
ms.openlocfilehash: a4db1e21f344f5cc58e2027b0816f9c8fb40b3bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519929"
---
# <a name="3110-ompgetnested-function"></a>3.1.10 Функция omp_get_nested

`omp_get_nested` Функция возвращает ненулевое значение, если включен вложенный параллелизм, а значение 0, если она отключена. Дополнительные сведения о вложенных параллелизма см. разделе 3.1.9 на странице 40. Он следующий:

```
#include <omp.h>
int omp_get_nested(void);
```

Если реализация не реализует вложенный параллелизм, эта функция всегда возвращает 0.