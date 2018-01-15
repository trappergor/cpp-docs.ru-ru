---
title: "Атомарная директива Using а.12 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9aa619d9bbe635a41d15a39d6c05780a4416520e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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