---
title: "Ошибка компилятора C3861 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3861"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3861"
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C3861
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

identifier: идентификатор не найден  
  
 Компилятору не удалось разрешить ссылку на идентификатор даже при поиске с зависимостью от аргументов.  
  
 Чтобы устранить эту ошибку, проверьте написание и регистр объявления идентификатора.  Убедитесь, что [операторы разрешения области действия](../../cpp/scope-resolution-operator.md) и [директивы using](../../misc/using-directive-cpp.md) пространства имен используются правильно.  Если идентификатор объявляется в файле заголовка, убедитесь, что заголовок включен до ссылки на него.  Кроме того, убедитесь, что идентификатор не исключен с помощью [директив условной компиляции](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3861:  
  
```  
// C3861.cpp  
void f2(){}  
int main() {  
   f();   // C3861  
   f2();   // OK  
}  
```  
  
## Пример  
 Классы исключений в стандартной библиотеке C\+\+ теперь находятся в пространстве имен `std`.  
  
```  
// C3861_b.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   try {  
      throw exception("Exception");   // C3861  
      // try the following line instead  
      // throw std::exception("Exception");  
   }  
   catch (...) {  
      std::cout << "caught an exception" << std::endl;  
   }  
}  
```