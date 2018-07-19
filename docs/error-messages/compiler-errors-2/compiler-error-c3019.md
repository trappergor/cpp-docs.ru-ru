---
title: Ошибка компилятора C3019 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3019
dev_langs:
- C++
helpviewer_keywords:
- C3019
ms.assetid: 31a6d9b6-d29f-4499-9ad8-48dd751e87c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 390a05af4c81104c081376d45f12f1a9cd8a91d4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33241762"
---
# <a name="compiler-error-c3019"></a>Ошибка компилятора C3019
шаг в OpenMP инструкции «for» имеет недопустимую форму  
  
 Приращение часть OpenMP `for` цикла должна использоваться переменная индекса как в левой и правой части оператора.  
  
 Следующий пример приводит к возникновению ошибки C3019:  
  
```  
// C3019.cpp  
// compile with: /openmp  
int main()  
{  
   int i = 0, j = 1, n = 3;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 10; i = j + n)   // C3019  
      // Try the following line instead:  
      // for (i = 0; i < 10; i++)  
         j *= 2;  
   }  
}  
```