---
title: "Ошибка компилятора C3038 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3038
dev_langs: C++
helpviewer_keywords: C3038
ms.assetid: 140ada3e-5636-43ef-a4ee-22a9f66a771f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 61cb06c7ebeff6dd24cdcd82026d09b5fd5d9a33
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3038"></a>Ошибка компилятора C3038
"переменная": переменная в предложении private не может быть редукционной переменной в охватывающем контексте  
  
 Переменная, используемая в предложении [reduction](../../parallel/openmp/reference/reduction.md) параллельной директивы, не может быть указана в предложении [private](../../parallel/openmp/reference/private-openmp.md) в директиве распределения рабочей нагрузки, которая привязывается к параллельной конструкции.  
  
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