---
title: A.5   Использование директивы critical
ms.date: 11/04/2016
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
ms.openlocfilehash: 82497d63acc057fbbcf26f585e42fc8611c08ec4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50545111"
---
# <a name="a5---using-the-critical-directive"></a>A.5   Использование директивы critical

Следующий пример содержит несколько `critical` директивы ([разделе 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) на странице 18). В примере показана модель организации очереди, в котором задачи удаляются из очереди и работали. Чтобы защититься от нескольких потоков, выведении ту же задачу, операция удаления должна находиться в `critical` разделе. Две очереди в этом примере не зависят от, надежно защищены с помощью `critical` директивы с разными именами *xaxis* и *ось y*.

```
#pragma omp parallel shared(x, y) private(x_next, y_next)
{
    #pragma omp critical ( xaxis )
        x_next = dequeue(x);
    work(x_next);
    #pragma omp critical ( yaxis )
        y_next = dequeue(y);
    work(y_next);
}
```