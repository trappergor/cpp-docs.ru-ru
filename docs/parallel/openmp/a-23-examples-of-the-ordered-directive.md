---
title: Примеры A.23 упорядоченный директивы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37cc4ea9db8cbd1a7bf095e2bde0ae482053a584
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="a23---examples-of-the-ordered-directive"></a>A.23   Примеры директивы ordered
Можно иметь несколько разделов упорядоченный с `for` задается с помощью `ordered` предложения. Первый пример не соответствует требованиям, так как API указывается следующее:  
  
 «Итерации цикла с `for` конструкция же не может выполняться `ordered` директив более чем один раз и он должен выполняться не более одного `ordered` директива.» (См. [раздел 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) на странице 22)  
  
 В этом примере несоответствующих всех итераций выполните упорядоченный разделами:  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
}  
```  
  
 Показано в следующем примере совместимые `for` более чем с одной упорядоченную часть:  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    if (i <= 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
    (i > 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
}  
```