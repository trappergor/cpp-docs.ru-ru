---
title: "Параллельные | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: parallel
dev_langs: C++
helpviewer_keywords: parallel OpenMP directive
ms.assetid: b8e90073-e85b-4d39-8ed8-0364441794fb
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 289a4928c9c46f6d758ddc2f30ed864488ab725e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="parallel"></a>parallel
Определяет параллельной области, который является код, который будет выполняться несколько потоков параллельно.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma omp parallel [clauses]  
{  
   code_block  
}  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `clause` (необязательно)  
 Ноль или несколько предложений.  . В разделе «Примечания» в список предложений, поддерживаемых **параллельных**.  
  
## <a name="remarks"></a>Примечания  
 **Параллельных** директива поддерживает следующие предложения OpenMP:  
  
-   [copyin](../../../parallel/openmp/reference/copyin.md)  
  
-   [default](../../../parallel/openmp/reference/default-openmp.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [if](../../../parallel/openmp/reference/if-openmp.md)  
  
-   [num_threads](../../../parallel/openmp/reference/num-threads.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
-   [reduction](../../../parallel/openmp/reference/reduction.md)  
  
-   [Общие](../../../parallel/openmp/reference/shared-openmp.md)  
  
 **Параллельные** также может использоваться с [разделы](../../../parallel/openmp/reference/sections-openmp.md) и [для](../../../parallel/openmp/reference/for-openmp.md) директивы.  
  
 Дополнительные сведения см. в разделе [2.3 конструкция parallel](../../../parallel/openmp/2-3-parallel-construct.md).  
  
## <a name="example"></a>Пример  
 Следующий пример показано, как настроить число потоков и определить параллельной области. По умолчанию количество потоков равно числу логических процессоров на компьютере. Например при наличии машины с одного физического процессора с технологией Hyper-Threading включена, он будет иметь два логических процессора и, следовательно, два потока.  
  
```  
// omp_parallel.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
int main() {  
   #pragma omp parallel num_threads(4)  
   {  
      int i = omp_get_thread_num();  
      printf_s("Hello from thread %d\n", i);  
   }  
}  
```  
  
```Output  
Hello from thread 0  
Hello from thread 1  
Hello from thread 2  
Hello from thread 3  
```  
  
## <a name="comment"></a>Комментарий  
 Обратите внимание, что порядок вывода могут различаться на разных компьютерах.  
  
## <a name="see-also"></a>См. также  
 [Директивы](../../../parallel/openmp/reference/openmp-directives.md)