---
title: "Ошибка компилятора C3016 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3016
dev_langs:
- C++
helpviewer_keywords:
- C3016
ms.assetid: 3423467e-e8bb-4f35-b4db-7925cafa74c1
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 49ccb5cc06a497103a62d6360ebddb16bc063bc7
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3016"></a>Ошибка компилятора C3016
"переменная": переменная индекса в операторе For директивы OpenMP должна иметь тип целого со знаком  
  
 Переменная индекса в операторе `for` директивы OpenMP должна иметь целочисленный тип со знаком.  
  
 Следующий пример приводит к возникновению ошибки C3016:  
  
```  
// C3016.cpp  
// compile with: /openmp  
int main()  
{  
   #pragma omp parallel  
   {  
      unsigned int i = 0;  
      // Try the following line instead:  
      // int i = 0;  
  
      #pragma omp for  
      for (i = 0; i <= 10; ++i)   // C3016  
      {  
      }  
   }  
}  
```
