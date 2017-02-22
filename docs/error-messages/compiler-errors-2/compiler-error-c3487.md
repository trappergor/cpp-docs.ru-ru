---
title: "Ошибка компилятора C3487 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3487"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3487"
ms.assetid: 39bda474-4418-4a79-98bf-2b22fa92eaaa
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C3487
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"возвращаемый тип": все возвращаемые выражения в лямбда\-выражении должны иметь один и тот же тип: ранее использовался "возвращаемый тип"  
  
 Лямбда\-выражение должно указывать возвращаемый тип, если оно содержит один оператор return.  Если лямбда\-выражение содержит несколько операторов return, они должны быть одного типа.  
  
### Исправление ошибки  
  
-   Укажите конечный возвращаемый тип для лямбда\-выражения.  Убедитесь, что все возвращаемые типа лямбда\-выражения относятся к одному типу или могут быть неявно преобразованы в тип возвращаемого значения.  
  
## Пример  
 В следующем примере возникает ошибка C3487, так как возвращаемые типы лямбда\-выражения не совпадают:  
  
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
  
## См. также  
 [Лямбда\-выражения](../../cpp/lambda-expressions-in-cpp.md)