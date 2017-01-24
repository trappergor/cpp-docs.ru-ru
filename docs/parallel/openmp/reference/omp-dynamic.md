---
title: "OMP_DYNAMIC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OMP_DYNAMIC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_DYNAMIC OpenMP environment variable"
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OMP_DYNAMIC
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Определяет, может ли время выполнения OpenMP может обрабатывать количество потоков в параллельной области.  
  
## Синтаксис  
  
```  
set OMP_DYNAMIC[=TRUE | =FALSE]  
```  
  
## Заметки  
 `OMP_DYNAMIC` переменная среды выполнения может быть переопределена  [omp\_set\_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md) функция.  
  
 По умолчанию в реализации Visual C\+\+ стандарта OpenMP `OMP_DYNAMIC=FALSE`.  
  
 Дополнительные сведения см. в разделе [4.3 OMP\_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md).  
  
## Пример  
 Следующая команда устанавливает `OMP_DYNAMIC` переменная среды значение TRUE.  
  
```  
set OMP_DYNAMIC=TRUE  
```  
  
 Следующая команда выводит текущий параметр `OMP_DYNAMIC` переменная среды:  
  
```  
set OMP_DYNAMIC  
```  
  
## См. также  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)