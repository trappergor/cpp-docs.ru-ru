---
title: "Ошибка компилятора C3018 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3018
dev_langs: C++
helpviewer_keywords: C3018
ms.assetid: 685be45f-f116-43a8-a88d-05ab6616e2f1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c99b0665ac5a4384c494b60fd78dc8fcf3ebc426
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3018"></a>Ошибка компилятора C3018
"переменная1": в проверке или в приращении в операторе For директивы OpenMP должна использоваться переменная индекса "переменная2"  
  
 Цикл `for` в операторе OpenMP должен использовать ту же переменную для проверки и увеличения, которую он использует для индекса.  
  
 При компиляции следующего примера возникнет ошибка C3018:  
  
```  
// C3018.cpp  
// compile with: /openmp  
int main()  
{  
   int i = 0, j = 5;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; j < 10; ++i)   // C3018  
      // try the the following line instead  
      // for (i = 0; i < 10; ++i)  
         j *= 2;  
  
      #pragma omp for  
      for (i = 0; i < 10; j = j + i)   // C3018  
      // try the the following line instead  
      // for (i = 0; i < 10; i = j + i)  
         j *= 2;  
   }  
}  
```