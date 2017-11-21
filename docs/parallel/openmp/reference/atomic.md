---
title: "atomic | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: atomic
dev_langs: C++
helpviewer_keywords: atomic OpenMP directive
ms.assetid: 275e0338-cf2f-4525-97b5-696250000df7
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 92804b2bdcc243bde6e536004cda73d7f5087b1d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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