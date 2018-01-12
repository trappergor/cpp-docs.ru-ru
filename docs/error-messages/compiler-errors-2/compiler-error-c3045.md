---
title: "Ошибка компилятора C3045 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3045
dev_langs: C++
helpviewer_keywords: C3045
ms.assetid: 9351ba3e-3d3f-455f-ac90-a810fa9fd947
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 71a669ef8c6547aeec68c9126d88844b2777e930
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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