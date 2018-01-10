---
title: "один | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Single
dev_langs: C++
helpviewer_keywords: single OpenMP directive
ms.assetid: 85cf94fb-cb9c-4d82-8609-adffa9f552e1
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8eabac06acc78aec46c86cf8a7dcbb2d5854c941
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="single"></a>одиночный
Позволяет указать, что фрагмент кода должна выполняться в одном потоке, не обязательно главного потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma omp single [clauses]   
{  
   code_block   
}  
```  
  
#### <a name="parameters"></a>Параметры  
 `clause` (необязательно)  
 Ноль или несколько предложений. . В разделе «Примечания» в список предложений, поддерживаемых **одного**.  
  
## <a name="remarks"></a>Примечания  
 **Одного** директива поддерживает следующие предложения OpenMP:  
  
-   [copyprivate](../../../parallel/openmp/reference/copyprivate.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
 [Master](../../../parallel/openmp/reference/master.md) директива позволяет указать, что фрагмент кода должен выполняться только для главного потока.  
  
 Дополнительные сведения см. в разделе [создания единого 2.4.3](../../../parallel/openmp/2-4-3-single-construct.md).  
  
## <a name="example"></a>Пример  
  
```  
// omp_single.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(2)  
   {  
      #pragma omp single  
      // Only a single thread can read the input.  
      printf_s("read input\n");  
  
      // Multiple threads in the team compute the results.  
      printf_s("compute results\n");  
  
      #pragma omp single  
      // Only a single thread can write the output.  
      printf_s("write output\n");  
    }  
}  
```  
  
```Output  
read input  
compute results  
compute results  
write output  
```  
  
## <a name="see-also"></a>См. также  
 [Директивы](../../../parallel/openmp/reference/openmp-directives.md)