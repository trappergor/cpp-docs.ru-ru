---
title: omp_set_nested | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_nested
dev_langs:
- C++
helpviewer_keywords:
- omp_set_nested OpenMP function
ms.assetid: fa1cb08c-7b8b-42c9-8654-2c33dcffb5b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6539167b936efdc4c9f407cd951c9c582b0a138
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
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