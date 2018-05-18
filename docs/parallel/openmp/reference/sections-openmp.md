---
title: разделы (OpenMP) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- section
- SECTIONS
dev_langs:
- C++
helpviewer_keywords:
- sections OpenMP directive
ms.assetid: 4cd1d776-e198-470e-930a-01fb0ab0a0bd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 60bc94685a7e6128e22cc3545ae8702abe6d472e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="sections-openmp"></a>sections (OpenMP)
Определяет разделы кода, чтобы разделить между всеми потоками.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma omp [parallel] sections [clauses]  
{  
   #pragma omp section  
   {  
      code_block   
   }   
}  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `clause` (необязательно)  
 Ноль или несколько предложений. . В разделе «Примечания» в список предложений, поддерживаемых **разделы**.  
  
## <a name="remarks"></a>Примечания  
 **Разделы** директива может содержать ноль или более **раздел** директивы.  
  
 **Разделы** директива поддерживает следующие предложения OpenMP:  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [lastprivate](../../../parallel/openmp/reference/lastprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
 Если **параллельных** также указан `clause` любые предложения, принимаются по **параллельных** или **разделы** директивы, за исключением `nowait`.  
  
 Дополнительные сведения см. в разделе [2.4.2 конструкция sections](../../../parallel/openmp/2-4-2-sections-construct.md).  
  
## <a name="example"></a>Пример  
  
```  
// omp_sections.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
    #pragma omp parallel sections num_threads(4)  
    {  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
        #pragma omp section  
        printf_s("Hello from thread %d\n", omp_get_thread_num());  
    }  
}  
```  
  
```Output  
Hello from thread 0  
Hello from thread 0  
```  
  
## <a name="see-also"></a>См. также  
 [Директивы](../../../parallel/openmp/reference/openmp-directives.md)