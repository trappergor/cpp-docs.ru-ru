---
title: Ошибка компилятора C3030 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3030
dev_langs:
- C++
helpviewer_keywords:
- C3030
ms.assetid: de92fd7e-29ba-46e8-b43b-f4b985cd74de
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97e49f413b850237998c9427be7982b36ec4146c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3030"></a>Ошибка компилятора C3030
"переменная": переменная в предложении или директиве "reduction" не может быть ссылочного типа  
  
 Вы можете передавать параметры значений только в некоторые предложения, такие как предложение reduction.  
  
 Следующий пример приводит к возникновению ошибки C3030:  
  
```  
// C3030.cpp  
// compile with: /openmp /link vcomps.lib  
#include "omp.h"  
  
void test(int &r) {  
   #pragma omp parallel reduction(+ : r)   // C3030  
      ;  
}  
  
void test2(int r) {  
   #pragma omp parallel reduction(+ : r)   // OK  
      ;  
}  
  
int main(int argc, char** argv) {  
   int& r = *((int*)argv);  
   int s = *((int*)argv);  
  
   #pragma omp parallel reduction(+ : r)   // C3030  
      ;  
  
   #pragma omp parallel reduction(+ : s)   // OK  
      ;  
}  
```