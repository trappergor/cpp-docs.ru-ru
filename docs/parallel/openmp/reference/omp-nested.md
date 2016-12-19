---
title: "OMP_NESTED | Microsoft Docs"
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
  - "OMP_NESTED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OMP_NESTED OpenMP environment variable"
ms.assetid: c43f5287-a548-40d0-bd54-0c6b2b9f9a53
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OMP_NESTED
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Указывает, включена ли вложенные параллелизм, если вложенные параллелизм не включена, либо заблокирована с `omp_set_nested`.  
  
## Синтаксис  
  
```  
set OMP_NESTED[=TRUE | =FALSE]  
```  
  
## Заметки  
 `OMP_NESTED` переменная среды выполнения может быть переопределена  [omp\_set\_nested](../../../parallel/openmp/reference/omp-set-nested.md) функция.  
  
 По умолчанию в реализации Visual C\+\+ стандарта OpenMP `OMP_DYNAMIC=FALSE`.  
  
 Дополнительные сведения см. в разделе [4.4 OMP\_NESTED](../Topic/4.4%20OMP_NESTED.md).  
  
## Пример  
 Следующая команда устанавливает `OMP_NESTED` переменная среды значение TRUE.  
  
```  
set OMP_NESTED=TRUE  
```  
  
 Следующая команда выводит текущий параметр `OMP_NESTED` переменная среды:  
  
```  
set OMP_NESTED  
```  
  
## См. также  
 [Environment Variables](../../../parallel/openmp/reference/openmp-environment-variables.md)