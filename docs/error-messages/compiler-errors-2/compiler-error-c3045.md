---
title: Ошибка компилятора C3045 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3045
dev_langs:
- C++
helpviewer_keywords:
- C3045
ms.assetid: 9351ba3e-3d3f-455f-ac90-a810fa9fd947
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93cdf51c7976dac0c1563a01a2111abea7e87042
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33249402"
---
# <a name="compiler-error-c3045"></a>Ошибка компилятора C3045
Ожидается составной оператор, следующий за директивой OpenMP "sections". Отсутствует "{"  
  
 Блок кода, ограниченный фигурными скобками, должен следовать за директивой [sections](../../parallel/openmp/reference/sections-openmp.md) .  
  
 Следующий пример приводит к возникновению ошибки C3045:  
  
```  
// C3045.cpp  
// compile with: /openmp /c  
#include "omp.h"  
  
int main() {  
   int n2 = 2, n3 = 3;  
  
   #pragma omp parallel  
   {  
      ++n2;  
  
      #pragma omp sections  
         ++n2;   // C3045  
  
      #pragma omp sections   // OK  
      {  
         ++n3;  
      }  
   }  
}  
```