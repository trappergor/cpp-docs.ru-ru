---
title: "3.1.1 omp_set_num_threads Function | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: b94cf2b5-8011-4a3b-ba56-676982642857
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 3.1.1 omp_set_num_threads Function
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`omp_set_num_threads` по умолчанию функция задает число потоков, используемых для последующих параллельных областей, которые не указывают a  `num_threads` предложение.  Формат следующий:  
  
```  
#include <omp.h>  
void omp_set_num_threads(int num_threads);  
```  
  
 Значение параметра *num\_threads* быть положительным целым числом.  Его результат зависит от того, включена ли динамическое изменение числа потоков.  Для исчерпывающего набора правил о функциональной совместимости между `omp_set_num_threads` функция и динамическую настройку потоков, см. шаг 2,3 на страницу 8.  
  
 Эта функция имеет эффекты, описанным выше вызывается из части программы, где `omp_in_parallel` функция возвращает ноль.  Если она вызывается из части программы, где `omp_in_parallel` не определена функция возвращает ненулевое значение, расширения функциональности этой функции.  
  
 Этот вызов имеет приоритет над `OMP_NUM_THREADS` переменная среды.  Значение по умолчанию для количества потоков, которые могут быть установлены с помощью вызова `omp_set_num_threads` либо, присвоив  `OMP_NUM_THREADS` переменная среды, можно явно переопределена на одном  **Параллельно** директива, указав  `num_threads` предложение.  
  
## Перекрестные ссылки:  
  
-   `omp_set_dynamic` функция см. в разделе  [Раздел 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на странице 39.  
  
-   `omp_get_dynamic` функция см. в разделе  [Раздел 3.1.8](../../parallel/openmp/3-1-8-omp-get-dynamic-function.md) на странице 40.  
  
-   `OMP_NUM_THREADS` переменная среды выполнения, см. в разделе  [Раздел 4.2](../../parallel/openmp/4-2-omp-num-threads.md) на странице 48 и шаг 2,3 на страницу 8.  
  
-   `num_threads` предложение см. в разделе  [Раздел 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8