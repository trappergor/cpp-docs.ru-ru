---
title: Ошибка компилятора C3020 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3020
dev_langs:
- C++
helpviewer_keywords:
- C3020
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2a9c942f6b1459cbdb88561b749290eb47d3cfb3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245372"
---
# <a name="compiler-error-c3020"></a>Ошибка компилятора C3020
«переменная»: переменная индекса из OpenMP цикла «for» нельзя изменять в теле цикла  
  
 OpenMP `for` цикла не может изменять индекс (счетчик цикла) в теле `for` цикла.  
  
 Следующий пример приводит к возникновению ошибки C3020:  
  
```  
// C3020.cpp  
// compile with: /openmp  
int main() {  
   int i = 0, n = 3;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 10; i += n)  
         i *= 2;   // C3020  
         // try the following line instead  
         // n++;  
   }  
}  
```  
  
 Переменная, объявленная с [lastprivate](../../parallel/openmp/reference/lastprivate.md) нельзя использовать в качестве индекса внутри Параллелизованный цикл.  
  
 Следующий пример даст C3020 для второй lastprivate, поскольку lastprivate, вызывающее запись в idx_a внутри самой внешней цикл for. Первый параметр lastprivate не вызывает ошибку, поскольку запись в idx_a за пределами внешнего цикла (с технической точки зрения в самом конце последней итерации). Следующий пример приводит к возникновению ошибки C3020.  
  
```  
// C3020b.cpp  
// compile with: /openmp /c  
float a[100][100];  
int idx_a, idx_b;  
void test(int first, int last)  
{  
   #pragma omp parallel for lastprivate(idx_a)  
   for (idx_a = first; idx_a <= last; ++idx_a) {  
      #pragma omp parallel for lastprivate(idx_a)   // C3020  
      for (idx_b = first; idx_b <= last; ++idx_b) {  
         a[idx_a][idx_b] += 1.0f;  
      }  
   }  
}  
```  
  
 В следующем примере показано возможное решение:  
  
```  
// C3020c.cpp  
// compile with: /openmp /c  
float a[100][100];  
int idx_a, idx_b;  
void test(int first, int last)  
{  
   #pragma omp parallel for lastprivate(idx_a)  
   for (idx_a = first; idx_a <= last; ++idx_a) {  
      #pragma omp parallel for lastprivate(idx_b)  
      for (idx_b = first; idx_b <= last; ++idx_b) {  
         a[idx_a][idx_b] += 1.0f;  
      }  
   }  
}  
```