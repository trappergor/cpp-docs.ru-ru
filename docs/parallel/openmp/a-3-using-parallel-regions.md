---
title: "Использование параллельных областей а.3 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 575216a1-960a-47f7-9c82-7f660291fcfe
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: be3489e924dab7faa50d26c7cb89af67b4034ca5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="a3---using-parallel-regions"></a>A.3   Использование параллельных регионов
`parallel` Директивы ([разделе 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8) можно использовать в крупных фрагментов данных параллельных программ. В следующем примере каждый поток в параллельной области решает, какую часть глобального массива `x` для работы, в зависимости от числа потоков:  
  
```  
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)  
{  
    iam = omp_get_thread_num();  
    np =  omp_get_num_threads();  
    ipoints = npoints / np;  
    subdomain(x, iam, ipoints);  
}  
```