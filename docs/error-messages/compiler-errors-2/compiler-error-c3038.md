---
title: "Ошибка компилятора сообщение об ошибке С3038 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3038
dev_langs:
- C++
helpviewer_keywords:
- C3038
ms.assetid: 140ada3e-5636-43ef-a4ee-22a9f66a771f
caps.latest.revision: 7
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
ms.openlocfilehash: d9aff323a1c00edb6646a6cd4b6125cc69a9418f
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3038"></a>Ошибка компилятора C3038
"переменная": переменная в предложении private не может быть редукционной переменной в охватывающем контексте  
  
 Переменные, которые отображаются в [сокращения](../../parallel/openmp/reference/reduction.md) предложение параллельной директивы не может быть указано в [частного](../../parallel/openmp/reference/private-openmp.md) предложение на директиву совместной работы, которая привязывается к параллельной конструкции.  
  
 Следующий пример приводит к возникновению ошибки C3038:  
  
```  
// C3038.cpp  
// compile with: /openmp /c  
int g_i, g_i2;  
  
int main() {  
   int i;  
  
   #pragma omp parallel reduction(+: g_i)  
   {  
      #pragma omp for private(g_i)   // C3038  
      // try the following line instead  
      // #pragma omp for private(g_i2)  
      for (i = 0; i < 10; ++i)  
         g_i += i;  
   }  
}  
```
