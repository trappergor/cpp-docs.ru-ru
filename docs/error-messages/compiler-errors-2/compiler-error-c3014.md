---
title: "Ошибка компилятора C3014 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3014
dev_langs: C++
helpviewer_keywords: C3014
ms.assetid: af1c5b0c-dbf9-4274-b06a-c6c2cdcf2a52
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e8d7191b6b8d48d06931fb286b96f9daec8abce9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3014"></a>Ошибка компилятора C3014
требуется цикл For, следующий за директивой OpenMP "директива"  
  
 Ошибкой будет указание непосредственно после директивы `for` чего-либо отличного от цикла `#pragma omp for` .  
  
 Следующий пример приводит к возникновению ошибки C3014.  
  
```  
// C3014.cpp  
// compile with: /openmp  
int main()  
{  
   int i = 0;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 10; ++i)   // OK  
      {  
      }  
   }  
  
   #pragma omp parallel for  
   for (i = 0; i < 10; ++i)   // OK  
   {  
   }  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      {   // C3014  
         for (i = 0; i < 10; ++i)  
         {  
         }  
      }  
   }  
  
   #pragma omp parallel for  
   {   // C3014  
      for (i = 0; i < 10; ++i)  
      {  
      }  
   }  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      i *= 2;   // C3014  
      for (i = 0; i < 10; ++i)  
      {  
      }  
   }  
  
   #pragma omp parallel for  
   i *= 2;   // C3014  
   for (i = 0; i < 10; ++i)  
   {  
   }  
}  
```