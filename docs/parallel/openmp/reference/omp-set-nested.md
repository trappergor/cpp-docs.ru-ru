---
title: omp_set_nested | Документация Майкрософт
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
ms.openlocfilehash: fc3506c35dca469febafe21509064abc1726d633
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116903"
---
# <a name="ompsetnested"></a>omp_set_nested
Использовать вложенные параллелизм.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void omp_set_nested(  
   int val  
);  
```  
  
### <a name="parameters"></a>Параметры
  
*Val*<br/>
Если значение ненулевое, обеспечивает поддержку вложенных параллелизма. Если значение равно нулю, отключает вложенных параллелизма.  
  
## <a name="remarks"></a>Примечания  
 Вложенные OMP параллелизма можно включить с помощью `omp_set_nested`, или установив [OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md) переменной среды.  
  
 Параметр для `omp_set_nested` переопределит параметр из `OMP_NESTED` переменной среды.  
  
 При включении переменную среды может нарушить приложения, в противном случае рабочей, так как число потоков растет в геометрической прогрессии при наличии вложенных параллельных регионов.  Например функции, что recurses 6 раз с количеством OMP потоков, равное 4 требуется 4096 (4 в степень 6) потоки в целом, снизится производительность приложения, если количество потоков превышает число процессоров. Единственным исключением бы привязанная приложений.  
  
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