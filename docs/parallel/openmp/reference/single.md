---
title: единый | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- Single
dev_langs:
- C++
helpviewer_keywords:
- single OpenMP directive
ms.assetid: 85cf94fb-cb9c-4d82-8609-adffa9f552e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7ff1a255933b79d39b6eedbb9362ff76a34e0f8a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716993"
---
# <a name="single"></a>одиночный
Позволяет указать, что раздела кода, должна выполняться в одном потоке, не обязательно главного потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma omp single [clauses]   
{  
   code_block   
}  
```  
  
#### <a name="parameters"></a>Параметры  

`clause`  
(Необязательно) Ноль или несколько предложений. См. в разделе "Примечания" для получения списка предложений, поддерживаемые **единый**.  
  
## <a name="remarks"></a>Примечания  
 **Единый** директива поддерживает следующие предложения OpenMP:  
  
-   [copyprivate](../../../parallel/openmp/reference/copyprivate.md)  
  
-   [firstprivate](../../../parallel/openmp/reference/firstprivate.md)  
  
-   [nowait](../../../parallel/openmp/reference/nowait.md)  
  
-   [private](../../../parallel/openmp/reference/private-openmp.md)  
  
 [Master](../../../parallel/openmp/reference/master.md) директива позволяет указать, что раздела кода, должны выполняться только для главного потока.  
  
 Дополнительные сведения см. в разделе [создать единый 2.4.3](../../../parallel/openmp/2-4-3-single-construct.md).  
  
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