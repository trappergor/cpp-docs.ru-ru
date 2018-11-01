---
title: A.1   Параллельное выполнение простого цикла
ms.date: 11/04/2016
ms.assetid: b8aaacae-b20d-4b16-a540-54ccbf09582b
ms.openlocfilehash: 5bd9a9c8b1d226c67f7e9031a547e551fae3407b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558942"
---
# <a name="a1---executing-a-simple-loop-in-parallel"></a>A.1   Параллельное выполнение простого цикла

В следующем примере показано, как для параллельного выполнения простого цикла с помощью `parallel for` директива ([разделе 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) на странице 16). Переменная итерации цикла является закрытым по умолчанию, поэтому нет необходимости явно указывать в предложения private.

```
#pragma omp parallel for
    for (i=1; i<n; i++)
        b[i] = (a[i] + a[i-1]) / 2.0;
```