---
title: 3.3.1 функция omp_get_wtime | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d71296d23df72464ed730713566c95e2403760a1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="331-ompgetwtime-function"></a>3.3.1 Функция omp_get_wtime
`omp_get_wtime` Функция возвращает значение двойной точности с плавающей запятой равно затраченное время по часам в секундах с момента некоторых «времени в прошлом».  Фактическое «время в прошлом» может быть произвольным, но оно не изменяются во время выполнения приложения. Он следующий:  
  
```  
#include <omp.h>  
double omp_get_wtime(void);  
```  
  
 Предполагается, что функция будет использоваться для измерения затраченного времени, как показано в следующем примере:  
  
```  
double start;  
double end;  
start = omp_get_wtime();  
... work to be timed ...  
end = omp_get_wtime();  
printf_s("Work took %f sec. time.\n", end-start);  
```  
  
 Возвращается выполняются «время потоков», которая предназначена, что они не должны быть глобально согласованного во всех потоках, участвующих в приложении.