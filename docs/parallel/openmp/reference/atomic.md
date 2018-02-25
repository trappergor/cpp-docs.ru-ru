---
title: "atomic | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atomic
dev_langs:
- C++
helpviewer_keywords:
- atomic OpenMP directive
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8cd00244d4668821942e7d6a9f6873652002bddb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="atomic"></a>атомарный
Указывает, что области памяти, которая будет обновляться автоматически.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma omp atomic  
   expression  
```  
  
#### <a name="parameters"></a>Параметры  
 `expression`  
 Инструкции, содержащей lvalue, расположение памяти, которую необходимо защитить от несколько операций записи. Дополнительные сведения о формах допустимые выражения см. в спецификации OpenMP.  
  
## <a name="remarks"></a>Примечания  
 `atomic` Директива поддерживает без предложения OpenMP.  
  
 Дополнительные сведения см. в разделе [2.6.4 atomic создания](../../../parallel/openmp/2-6-4-atomic-construct.md).  
  
## <a name="example"></a>Пример  
  
```  
// omp_atomic.cpp  
// compile with: /openmp   
#include <stdio.h>  
#include <omp.h>  
  
#define MAX 10  
  
int main() {  
   int count = 0;  
   #pragma omp parallel num_threads(MAX)  
   {  
      #pragma omp atomic  
      count++;  
   }  
   printf_s("Number of threads: %d\n", count);  
}  
```  
  
```Output  
Number of threads: 10  
```  
  
## <a name="see-also"></a>См. также  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)