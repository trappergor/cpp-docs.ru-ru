---
title: С помощью lastprivate предложение A.6 | Документы Microsoft
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
ms.openlocfilehash: eec6ddc46aab36671e767963e5aaf6e25c4d25cd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="a6---using-the-lastprivate-clause"></a>A.6   Использование предложения lastprivate
Иногда для правильного выполнения зависит от значения, последней итерации цикла присваивается переменной. Такие программы необходимо перечислить все переменные, такие как аргументы для `lastprivate` предложение ([раздел 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) на стр.), чтобы значения переменных совпадают при последовательного выполнения цикла.  
  
```  
#pragma omp parallel  
{  
   #pragma omp for lastprivate(i)  
      for (i=0; i<n-1; i++)  
         a[i] = b[i] + b[i+1];  
}  
a[i]=b[i];  
```  
  
 В предыдущем примере значение `i` в конце параллельной области будут равны `n-1`, как в случае последовательного.