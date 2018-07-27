---
title: Ошибка компилятора C3499 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3499
dev_langs:
- C++
helpviewer_keywords:
- C3499
ms.assetid: 6717de5c-ae0f-4024-bdf2-b5598009e7b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de299c5da66790276433da22227a3aa97cb55c82
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33257462"
---
# <a name="compiler-error-c3499"></a>Ошибка компилятора C3499
заданное лямбда-выражение с возвращаемым типом void не может возвращать значение  
  
 Компилятор создает эту ошибку, когда лямбда-выражение, которое указывает `void` в качестве типа возвращаемого значения, возвращает значение; или когда лямбда-выражение содержит несколько операторов и возвращает значение, но не указывает его тип.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Не возвращайте значение из лямбда-выражения.  
  
-   Либо укажите тип возвращаемого значения лямбда-выражения.  
  
-   Либо объедините операторы, которые составляют текст лямбда-выражения, в один оператор.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C3499, так как текст лямбда-выражения содержит несколько инструкций и возвращает значение, но лямбда-выражение не указывает тип возвращаемого значения:  
  
```  
// C3499a.cpp  
  
int main()  
{  
   [](int x) { int n = x * 2; return n; } (5); // C3499  
}  
```  
  
## <a name="example"></a>Пример  
 В следующем примере показано два возможных способа устранения ошибки C3499. В первом решении указывается тип возвращаемого значения лямбда-выражения. Во втором решении объединяются операторы, которые составляют лямбда-выражение, в один оператор.  
  
```  
// C3499b.cpp  
  
int main()  
{  
   // Possible resolution 1:   
   // Provide the return type of the lambda expression.  
   [](int x) -> int { int n = x * 2; return n; } (5);  
  
   // Possible resolution 2:   
   // Combine the statements that make up the body of   
   // the lambda expression into a single statement.  
   [](int x) { return x * 2; } (5);  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)