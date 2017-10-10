---
title: "Ошибка компилятора C3033 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3033
dev_langs:
- C++
helpviewer_keywords:
- C3033
ms.assetid: 8628b6bb-a650-4ed2-af13-57acd2f7ddbb
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c005874c7a11f5ec250daa42f8857070bbfad8dc
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3033"></a>Ошибка компилятора C3033
"переменная": переменная в предложении "предложение" не может иметь тип, квалифицированный как const  
  
 Значения, передаваемые в некоторые предложения, не могут быть переменными `const` .  
  
 Следующий пример приводит к возникновению ошибки C3033:  
  
```  
// C3033.cpp  
// compile with: /openmp /link vcomps.lib  
int main() {  
   const int val = 1;  
   int val2 = 1;  
  
   #pragma omp parallel reduction(+ : val)   // C3033  
   ;  
  
   #pragma omp parallel reduction(+ : val2)   // OK  
   ;  
}  
```
