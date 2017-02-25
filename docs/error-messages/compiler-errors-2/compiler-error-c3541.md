---
title: "Ошибка компилятора C3541 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3541"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3541"
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3541
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": невозможно применить оператор typeid к типу, содержащему "auto"  
  
 Оператор [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md) нельзя применить к указанному типу, поскольку он содержит описатель `auto`.  
  
## Пример  
 Следующий пример вызывает ошибку C3541.  
  
```  
// C3541.cpp  
// Compile with /Zc:auto  
#include <typeinfo>  
int main() {  
    auto x = 123;  
    typeid(x);    // OK  
    typeid(auto); // C3541  
    return 0;  
}  
```  
  
## См. также  
 [Ключевое слово auto](../../cpp/auto-keyword.md)   
 [\/Zc:auto \(выведение типа переменной\)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [typeid](../Topic/typeid%20%20\(C++%20Component%20Extensions\).md)