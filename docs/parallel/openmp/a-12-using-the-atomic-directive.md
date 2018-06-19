---
title: Атомарная директива Using а.12 | Документы Microsoft
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
ms.openlocfilehash: 719d7a9843a0759b5a5bd558e07a2004f9ef1543
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33691419"
---
# <a name="a12---using-the-atomic-directive"></a>A.12   Использование директивы atomic
Следующий пример позволяет избежать состояния гонки (одновременное обновление элемент *x* из нескольких потоков) с помощью `atomic` директивы ([раздел 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md) на странице 19):  
  
```  
#pragma omp parallel for shared(x, y, index, n)  
    for (i=0; i<n; i++)   
    {  
        #pragma omp atomic  
            x[index[i]] += work1(i);  
        y[i] += work2(i);  
    }  
```  
  
 Преимущество использования `atomic` директивы в этом примере является то, что обновления двух разных элементов x, чтобы выполняться параллельно. Если `critical` директивы ([раздел 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) на странице 18) были использованы, а затем обновляет все элементы *x* будут выполняться последовательно (хотя в любом не гарантирует порядок).  
  
 Обратите внимание, что `atomic` директива применяется только к сразу после инструкции C или C++.  В результате элементы *y* не обновляются автоматически в этом примере.