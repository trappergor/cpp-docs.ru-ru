---
title: "4.3 OMP_DYNAMIC | Microsoft Docs"
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
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 4.3 OMP_DYNAMIC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**OMP\_DYNAMIC** переменная среды включение или отключение динамическую корректировку числа потоков, доступных для выполнения параллельных областей, если явно не разрешена динамическая корректировка или заблокирована путем вызова  **omp\_set\_dynamic** библиотечная процедура.  Его значение должно представлять **True** OR  **False**.  
  
 Если задано значение **True**число потоков, используемых для выполнения параллельных области может быть изменяется средой выполнения для наилучшего использует системные ресурсы.  Если задано значение **False**динамическая корректировка заблокирована.  Состояние по умолчанию реализация\-определено.  
  
 Пример:  
  
```  
setenv OMP_DYNAMIC TRUE  
```  
  
## Перекрестные ссылки:  
  
-   Дополнительные сведения о параллельных областях см. в разделе [Раздел 2.3](../../parallel/openmp/2-3-parallel-construct.md) на странице 8.  
  
-   **omp\_set\_dynamic** функция см. в разделе  [Раздел 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) на странице 39.