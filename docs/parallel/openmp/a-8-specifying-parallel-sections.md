---
title: A.8   Указание параллельных разделов
ms.date: 11/04/2016
ms.assetid: cf399304-121e-4c07-9829-47e0dbc2ef10
ms.openlocfilehash: 81eaed920e77b23052ac58c2d0e18fee83c00565
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461442"
---
# <a name="a8---specifying-parallel-sections"></a>A.8   Указание параллельных разделов

В следующем примере (для [разделе 2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) на странице 14) функции *xaxis*, *ось y*, и *zaxis* могут быть выполнены одновременно. Первый `section` директива является необязательным.  Обратите внимание, что все `section` директивы должна отображаться в лексическую область `parallel sections` построения.

```
#pragma omp parallel sections
{
    #pragma omp section
        xaxis();
    #pragma omp section
        yaxis();
    #pragma omp section
        zaxis();
}
```