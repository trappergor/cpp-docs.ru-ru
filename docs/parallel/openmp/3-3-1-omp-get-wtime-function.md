---
title: "3.3.1 функция omp_get_wtime | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0f89a71d1b91a27dfdd0abf13be4a5f0e30b3fd9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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