---
title: "num_threads | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: num_threads
dev_langs: C++
helpviewer_keywords: num_threads OpenMP clause
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d07c2f59572b5e771013d5162f974d865ed97880
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="numthreads"></a>num_threads
Задает число потоков в поток команды.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
num_threads(num)  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `num`  
 Число потоков  
  
## <a name="remarks"></a>Примечания  
 `num_threads` Предложение имеет ту же функциональность, что [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) функции.  
  
 `num_threads`применяется к следующие директивы:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [разделы](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.3 конструкция parallel](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Пример  
 В разделе [параллельных](../../../parallel/openmp/reference/parallel.md) пример использования `num_threads` предложения.  
  
## <a name="see-also"></a>См. также  
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)