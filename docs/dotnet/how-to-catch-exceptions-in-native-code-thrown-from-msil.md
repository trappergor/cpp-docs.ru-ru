---
title: "Практическое руководство. Исключения в машинном коде, создаваемые MSIL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "перехват исключений, создано из MSIL"
  - "исключения, перехват"
  - "MSIL, перехват исключений в машинном коде"
ms.assetid: c15afd2b-8505-43bf-8a4a-f1d41532a124
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Исключения в машинном коде, создаваемые MSIL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В машинном коде можно перехватить исключение C\+\+ собственное из кода MSIL.  Можно также перехватывать исключения среды CLR с `__try` и `__except`.  
  
 Дополнительные сведения см. в разделах [Структурированная обработка исключений](../cpp/structured-exception-handling-c-cpp.md) и [Обработка исключений С\+\+](../cpp/cpp-exception-handling.md).  
  
## Пример  
 В следующем примере определяется модуля с функциями, 2 из которых создает собственное исключение и другие, вызывающее исключение MSIL.  
  
```  
// catch_MSIL_in_native.cpp  
// compile with: /clr /c  
void Test() {  
   throw ("error");  
}  
  
void Test2() {  
   throw (gcnew System::Exception("error2"));  
}  
```  
  
## Пример  
 В следующем примере определяется модуль, который перехватывает исключение для исключения и MSIL.  
  
```  
// catch_MSIL_in_native_2.cpp  
// compile with: /clr catch_MSIL_in_native.obj  
#include <iostream>  
using namespace std;  
void Test();  
void Test2();  
  
void Func() {  
   // catch any exception from MSIL  
   // should not catch Visual C++ exceptions like this  
   // runtime may not destroy the object thrown  
   __try {  
      Test2();  
   }  
   __except(1) {  
      cout << "caught an exception" << endl;  
   }  
  
}  
  
int main() {  
   // catch native C++ exception from MSIL  
   try {  
      Test();  
   }  
   catch(char * S) {  
      cout << S << endl;  
   }  
   Func();  
}  
```  
  
  **error**  
**уловил исключение**   
## См. также  
 [Обработка исключений](../windows/exception-handling-cpp-component-extensions.md)