---
title: "C3499 Ошибка компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3499
dev_langs:
- C++
helpviewer_keywords:
- C3499
ms.assetid: 6717de5c-ae0f-4024-bdf2-b5598009e7b6
caps.latest.revision: 8
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 51213128e2f0492f4b296c1abbfac0cdab214174
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

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
