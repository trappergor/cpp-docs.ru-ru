---
title: A.12   Использование директивы atomic
ms.date: 11/04/2016
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
ms.openlocfilehash: 0f75b182e2cae11f0e72d5ca1e67f887294e8f69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504449"
---
# <a name="a12---using-the-atomic-directive"></a>A.12   Использование директивы atomic

Следующий пример позволяет избежать состояния гонки (одновременное обновление элемента *x* несколькими потоками) с помощью `atomic` директива ([разделе 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md) на странице 19):

```
#pragma omp parallel for shared(x, y, index, n)
    for (i=0; i<n; i++)
    {
        #pragma omp atomic
            x[index[i]] += work1(i);
        y[i] += work2(i);
    }
```

Преимущество использования `atomic` директивы в этом примере является то, что обновление двух разных элементов x возникает в параллельном режиме. Если `critical` директива ([разделе 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) на странице 18) использовались, а затем обновляет все элементы *x* будет выполняться последовательно (хотя в любом не гарантирует порядок).

Обратите внимание, что `atomic` команда применяется только для немедленно следующий за ним оператор C или C++.  В результате элементы *y* атомарным образом не обновляются в этом примере.