---
title: omp_set_dynamic | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_set_dynamic
dev_langs:
- C++
helpviewer_keywords:
- omp_set_dynamic OpenMP function
ms.assetid: 3845faf2-a0ca-45a5-ae70-2a7a6164f1e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3e8ac574ce304238affbab41acc415e1d8de697
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026911"
---
# <a name="ompsetdynamic"></a>omp_set_dynamic
Указывает, что количество потоков, доступных в последующих параллельной области могут быть изменены при время выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void omp_set_dynamic(  
   int val  
);  
```  
  
### <a name="parameters"></a>Параметры
  
*Val*<br/>
Значение, указывающее, если количество потоков, доступных в последующих параллельной области могут быть изменены при выполнении.  Если значение ненулевое, среда выполнения можно изменить число потоков, если значение равно нулю, среда выполнения не будет динамически корректировать число потоков.  
  
## <a name="remarks"></a>Примечания  
 Число потоков никогда не превысит значение, заданное параметром [omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md) или [OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md).  
  
 Используйте [omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md) для отображения текущего значения параметра `omp_set_dynamic`.  
  
 Параметр для `omp_set_dynamic` переопределит параметр из [OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md) переменной среды.  
  
 Дополнительные сведения см. в разделе [3.1.7 функция omp_set_dynamic](../../../parallel/openmp/3-1-7-omp-set-dynamic-function.md).  
  
## <a name="example"></a>Пример  
  
```  
// omp_set_dynamic.cpp  
// compile with: /openmp  
#include <stdio.h>  
#include <omp.h>  
  
int main()   
{  
    omp_set_dynamic(9);  
    omp_set_num_threads(4);  
    printf_s("%d\n", omp_get_dynamic( ));  
    #pragma omp parallel  
        #pragma omp master  
        {  
            printf_s("%d\n", omp_get_dynamic( ));  
        }  
}  
```  
  
```Output  
1  
1  
```  
  
## <a name="see-also"></a>См. также  
 [Функции](../../../parallel/openmp/reference/openmp-functions.md)