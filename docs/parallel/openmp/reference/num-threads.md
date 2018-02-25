---
title: "num_threads | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- num_threads
dev_langs:
- C++
helpviewer_keywords:
- num_threads OpenMP clause
ms.assetid: 09a56fc8-25c7-43e4-bbb5-71cb955d0b93
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3b9d12b8216033b5ffe6499290f1c2b5742152b2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
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
  
 `num_threads` применяется к следующие директивы:  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [Разделы](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.3 конструкция parallel](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Пример  
 В разделе [параллельных](../../../parallel/openmp/reference/parallel.md) пример использования `num_threads` предложения.  
  
## <a name="see-also"></a>См. также  
 [Предложения](../../../parallel/openmp/reference/openmp-clauses.md)