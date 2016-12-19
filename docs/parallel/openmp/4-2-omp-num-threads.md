---
title: "4.2 OMP_NUM_THREADS | Microsoft Docs"
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
ms.assetid: 49dd55dd-25d5-4a5a-a998-cc7f47b2dae2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 4.2 OMP_NUM_THREADS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**OMP\_NUM\_THREADS** переменная среды выполнения присваивает по умолчанию количество потоков для использования во время выполнения, если это число не был явно изменен путем вызова  **omp\_set\_num\_threads** библиотечная подпрограмма или явной  **num\_threads** предложение on a  **Параллельно** директива.  
  
 Значение  OMP\_NUM\_THREADS переменная среды должно быть положительным целым числом.  Его результат зависит от того, включена ли динамическое изменение числа потоков.  Для исчерпывающего набора правил о функциональной совместимости между OMP\_NUM\_THREADS переменная среды и динамическую настройку потоков, см. шаг 2,3 на страницу 8.  
  
 Если не указано никакого значения, OMP\_NUM\_THREADS реализация\-определена переменная среды или если указанное значение не является положительным целым числом или если значение превышает максимальное количество потоков, система может поддерживать, то количество потоков для использования.  
  
 Пример:  
  
```  
setenv OMP_NUM_THREADS 16  
```  
  
## Перекрестные ссылки:  
  
-   **num\_threads** предложение см. в разделе  [Раздел 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8.  
  
-   **omp\_set\_num\_threads** функция см. в разделе  [Раздел 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) на странице 36.  
  
-   **omp\_set\_dynamic** функция см. в разделе  [Раздел 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на странице 39.