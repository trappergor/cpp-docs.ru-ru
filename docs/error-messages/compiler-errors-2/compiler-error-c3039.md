---
title: Ошибка компилятора C3039 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3039
dev_langs:
- C++
helpviewer_keywords:
- C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2bdcfa36d270dc842eec0508969c650e7b30bee4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33243728"
---
# <a name="compiler-error-c3039"></a>Ошибка компилятора C3039
"переменная": переменная индекса в операторе for директивы OpenMP не может быть редукционной переменной  
  
 Переменная индекса является неявно частной, поэтому ее нельзя использовать в предложении [reduction](../../parallel/openmp/reference/reduction.md) в заключающей директиве [parallel](../../parallel/openmp/reference/parallel.md) .  
  
## <a name="example"></a>Пример  
 При компиляции следующего примера возникнет ошибка C3039:  
  
```  
// C3039.cpp  
// compile with: /openmp /c  
int g_i;  
  
int main() {  
   int i;  
  
   #pragma omp parallel reduction(+: i)  
   {  
      #pragma omp for  
      for (i = 0; i < 10; ++i)   // C3039  
         g_i += i;  
   }  
}  
```