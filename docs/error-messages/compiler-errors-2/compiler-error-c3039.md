---
title: "C3039 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3039
dev_langs:
- C++
helpviewer_keywords:
- C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 6d935f373201831c2689b5dbbc072955afd30415
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3039"></a>Ошибка компилятора C3039
"переменная": переменная индекса в операторе for директивы OpenMP не может быть редукционной переменной  
  
 Переменная индекса неявно закрытым, поэтому переменная не может использоваться в [сокращения](../../parallel/openmp/reference/reduction.md) предложение в конечном [параллельных](../../parallel/openmp/reference/parallel.md) директивы.  
  
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
