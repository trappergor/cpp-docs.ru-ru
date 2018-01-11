---
title: "omp_set_nested | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: omp_set_nested
dev_langs: C++
helpviewer_keywords: omp_set_nested OpenMP function
ms.assetid: fa1cb08c-7b8b-42c9-8654-2c33dcffb5b6
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f08fec246b5df4b5a6dc965917e0a6438b58042f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ompsetnested"></a>omp_set_nested
Включает вложенные параллелизма.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void omp_set_nested(  
   int val  
);  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 `val`  
 Если значение ненулевое, обеспечивает поддержку вложенных параллелизма. Если значение равно нулю, отключает вложенный параллелизм.  
  
## <a name="remarks"></a>Примечания  
 Вложенные OMP параллелизма может быть включен с `omp_set_nested`, или установив [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md) переменной среды.  
  
 Параметр для `omp_set_nested` переопределит параметр `OMP_NESTED` переменной среды.  
  
 При включении переменной среды может нарушить работу приложения, в противном случае оперативной число потоков, увеличивается экспоненциально, при наличии вложенных параллельных областей.  Например, recurses 6 раз с OMP потоков, равным 4 требует 4096 (4 в степень 6) функции потоков в общем, снизит производительность приложения, если количество потоков превышает число процессоров. Единственным исключением бы бы ввода / вывода приложений.  
  
 Используйте [omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md) для отображения текущего значения параметра `omp_set_nested`.  
  
 Дополнительные сведения см. в разделе [3.1.9 функция omp_set_nested](../../../parallel/openmp/3-1-9-omp-set-nested-function.md).  
  
## <a name="example"></a>Пример  
  
```  
// omp_set_nested.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main( )   
{  
    omp_set_nested(1);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_nested( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_nested( ));  
        }  
}  
```  
  
```Output  
1  
1  
```  
  
## <a name="see-also"></a>См. также  
 [Функции](../../../parallel/openmp/reference/openmp-functions.md)