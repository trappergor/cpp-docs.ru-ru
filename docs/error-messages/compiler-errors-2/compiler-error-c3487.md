---
title: "Ошибка компилятора C3487 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3487
dev_langs: C++
helpviewer_keywords: C3487
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: eb659f2d7971d1dd2ff27c438839336d4744767e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3487"></a>Ошибка компилятора C3487
"тип возвращаемого значения": все возвращаемые выражения в лямбда-выражении должны иметь один и тот же тип: ранее использовался "тип возвращаемого значения"  
  
 Лямбда-выражение должно указывать тип возвращаемого значения, если оно содержит один оператор return. Если лямбда-выражение содержит несколько операторов return, они должны быть одного типа.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Укажите конечный возвращаемый тип для лямбда-выражения. Убедитесь, что все возвращаемые типа лямбда-выражения относятся к одному типу или могут быть неявно преобразованы в тип возвращаемого значения.  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3487, так как типы возвращаемого значения лямбда-выражения не совпадают:  
  
```  
// C3487.cpp  
// Compile by using: cl /c /W4 C3487.cpp  
  
int* test(int* pi) {  
   // To fix the error, uncomment the trailing return type below  
   auto odd_pointer = [=]() /* -> int* */ {  
      if (*pi % 2)   
         return pi;  
      return nullptr; // C3487 - nullptr is not an int* type  
   };  
   return odd_pointer();  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Лямбда-выражения](../../cpp/lambda-expressions-in-cpp.md)