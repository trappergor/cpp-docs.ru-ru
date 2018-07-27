---
title: Ошибка компилятора C3005 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3005
dev_langs:
- C++
helpviewer_keywords:
- C3005
ms.assetid: 30bad565-e79f-4c3f-82cb-a74bd0baab8f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80c0bdb0f17670c5acd178b7eadcbc6d3868637c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245204"
---
# <a name="compiler-error-c3005"></a>Ошибка компилятора C3005
"текст_ошибки": непредвиденная лексема в директиве OpenMP "директива"  
  
 Директива OpenMP сформирована неправильно.  
  
 В следующем примере возникает ошибка C3005:  
  
```  
// C3005.c  
// compile with: /openmp  
int main()  
{  
   #pragma omp parallel + for   // C3005  
}  
```  
  
 Ошибка C3005 также может возникать, если поместить открывающую фигурную скобку в одной строке с директивой pragma.  
  
```  
// C3005b.c  
// compile with: /openmp  
int main() {  
   #pragma omp parallel {   // C3005 put open brace on next line  
   lbl2:;  
   }  
   goto lbl2;  
}  
```