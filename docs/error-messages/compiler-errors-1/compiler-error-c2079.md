---
title: "Ошибка компилятора C2079 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2079"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2079"
ms.assetid: ca58d6d5-eccd-40b7-ba14-c003223c5bc7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C2079
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

для "идентификатора" использовано неопределенное "имя" класса, структуры или объединения  
  
 Указанный идентификатор является неопределенным классом, структурой или объединением.  
  
 Эта ошибка может возникать при инициализации безымянного объединения.  
  
 Следующий пример приводит к возникновению ошибки C2079:  
  
```  
// C2079.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   std::ifstream g;   // C2079  
}  
```  
  
 Возможный способ устранения данной ошибки:  
  
```  
// C2079b.cpp  
// compile with: /EHsc  
#include <fstream>  
int main( ) {  
   std::ifstream g;  
}  
```  
  
 Ошибка C2079 также может возникать при попытке объявления стекового объекта типа, для которого в области видимости находится только предварительное объявление.  
  
```  
// C2079c.cpp  
class A;  
  
class B {  
   A a;   // C2079  
};  
  
class A {};  
```  
  
 Возможный способ устранения данной ошибки:  
  
```  
// C2079d.cpp  
// compile with: /c  
class A;  
class C {};  
  
class B {  
   A * a;  
   C c;  
};  
  
class A {};  
```