---
title: Ошибка компилятора C2675 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2675
dev_langs:
- C++
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb949f5d6ab5881b911bab89150ae13f47443fcf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2675"></a>Ошибка компилятора C2675
унарный «оператор»: «тип» не определяет этот оператор или преобразование к типу приемлемо к встроенному оператору  
  
 C2675 также может возникнуть при использовании унарного оператора, а тип не определяет оператор или преобразование к типу приемлемо к встроенному оператору. Чтобы использовать этот оператор, необходимо перегрузить его для указанного типа или определить преобразование в тип, для которого определен оператор.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2675.  
  
```  
// C2675.cpp  
struct C {   
   C(){}  
} c;  
  
struct D {   
   D(){}  
   void operator-(){}  
} d;  
  
int main() {  
   -c;   // C2675  
   -d;   // OK  
}  
```