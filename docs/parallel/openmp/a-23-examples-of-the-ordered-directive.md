---
title: A.23   Примеры директивы ordered
ms.date: 11/04/2016
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
ms.openlocfilehash: 2868b771fd57613981f3c6458b48493a1b26eee4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472284"
---
# <a name="a23---examples-of-the-ordered-directive"></a>A.23   Примеры директивы ordered

Можно иметь несколько упорядоченных разделов с `for` указывается с помощью `ordered` предложение. Первый пример соответствует требованиям, так как API указывается следующее:

«Итерация цикла с `for` конструкция же не может выполняться `ordered` директив более чем один раз и он должен выполняться не более одного `ordered` директива.» (См. в разделе [разделе 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) на стр. 22)

В этом примере несоответствующих все итерации выполняются упорядоченный разделами:

```
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    #pragma omp ordered
    { ... }
    ...
    #pragma omp ordered
    { ... }
    ...
}
```

Показано в следующем примере соответствует `for` с более чем один раздел с контролем порядка:

```
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    if (i <= 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
    (i > 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
}
```