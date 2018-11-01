---
title: A.6   Использование предложения lastprivate
ms.date: 11/04/2016
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
ms.openlocfilehash: 7d5ba1413827590b7fb3afa0847b9aa1da3c41e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579810"
---
# <a name="a6---using-the-lastprivate-clause"></a>A.6   Использование предложения lastprivate

Иногда для правильного выполнения зависит от значения, последней итерации цикла присваивается переменной. Таких программ должен перечислить все такие переменные в качестве аргументов `lastprivate` предложение ([разделе 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) на стр. 27) таким образом, значения переменных так же, как при выполнении цикла последовательно.

```
#pragma omp parallel
{
   #pragma omp for lastprivate(i)
      for (i=0; i<n-1; i++)
         a[i] = b[i] + b[i+1];
}
a[i]=b[i];
```

В предыдущем примере, значение `i` в конце параллельной области будут равны `n-1`, как показано в последовательном.