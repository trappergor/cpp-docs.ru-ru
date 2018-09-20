---
title: A.5 Использование директивы critical | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99f9ab513ae1df5a7e1e62cfefcefe404637c063
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444571"
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