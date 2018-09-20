---
title: A.12 использование директивы atomic | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04daed582cfe87f6e4803b30919af3e07037de7f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378752"
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