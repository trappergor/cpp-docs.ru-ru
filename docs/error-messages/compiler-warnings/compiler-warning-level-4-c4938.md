---
title: "Предупреждение компилятора (уровень 4) C4938 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4938"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4938"
ms.assetid: 6acac81a-9d23-465e-b700-ed4b6e8edcd0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 4) C4938
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"переменная": переменная сокращения формата с плавающей точкой может привести к несогласованным результатам при использовании \/fp:strict или \#pragma fenv\_access  
  
 Не следует использовать [\/fp: strict](../../build/reference/fp-specify-floating-point-behavior.md) или [fenv\_access](../../preprocessor/fenv-access.md) с сокращениями чисел с плавающей запятой OpenMP, так как сумма вычисляется в другом порядке. Таким образом, результаты могут отличаться от результатов вычислений без использования параметра \/openmp.  
  
 При компиляции следующего примера будет выдано предупреждение C4938:  
  
```  
// C4938.cpp // compile with: /openmp /W4 /fp:strict /c // #pragma fenv_access(on) extern double *a; double test(int first, int last) { double sum = 0.0; #pragma omp parallel for reduction(+: sum)   // C4938 for (int i = first ; i <= last ; ++i) sum += a[i]; return sum; }  
```  
  
 Без явной параллелизации сумма вычисляется следующим образом:  
  
```  
sum = a[first] + a[first + 1] + ... + a[last];   
```  
  
 С явной параллелизацией \(и двумя потоками\) сумма вычисляется следующим образом:  
  
```  
sum1 = a[first] + ... a[first + last / 2]; sum2 = a[(first + last / 2) + 1] + ... a[last]; sum = sum1 + sum2;  
```