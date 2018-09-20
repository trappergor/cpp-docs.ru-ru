---
title: A.6 использование предложения lastprivate | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03d18d3aaf5c5d1cbe03282710ae4f4e2bb613f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390583"
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