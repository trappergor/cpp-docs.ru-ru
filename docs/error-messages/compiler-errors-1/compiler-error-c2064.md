---
title: "Ошибка компилятора C2064 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2064"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2064"
ms.assetid: 6cda05da-f437-4f50-9813-ae69538713a3
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2064
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

результатом вычисления фрагмента не является функция, принимающая N аргументов  
  
 Вызов функции через выражение.  Выражение не получает указатель на функцию, которая принимает указанное число аргументов.  
  
 В этом примере код пытается вызвать не функции как функции.  Следующий пример приводит к возникновению ошибки C2064.  
  
```  
// C2064.cpp  
int i, j;  
char* p;  
void func() {  
   j = i();    // C2064, i is not a function  
   p();        // C2064, p doesn't point to a function  
}  
```  
  
 Указатели на нестатические функции\-члены необходимо вызывать из контекста экземпляра объекта.  В следующем примере показано возникновение ошибки C2064 и приводятся сведения по ее устранению.  
  
```  
// C2064b.cpp  
struct C {  
   void func1(){}  
   void func2(){}  
};  
  
typedef void (C::*pFunc)();  
  
int main() {  
   C c;  
   pFunc funcArray[2] = {&C::func1, &C::func2};  
   (funcArray[0])();    // C2064   
   (c.*funcArray[0])(); // OK - function called in instance context  
}  
  
```  
  
 В классе указатели на функции\-члены также должны указывать контекст вызывающего объекта.  В следующем примере показано возникновение ошибки C2064 и приводятся сведения по ее устранению.  
  
```  
// C2064d.cpp  
// Compile by using: cl /c /W4 C2064d.cpp  
struct C {  
   typedef void (C::*pFunc)();  
   pFunc funcArray[2];  
   void func1(){}  
   void func2(){}  
   C() {  
      funcArray[0] = &C::func1;  
      funcArray[1] = &C::func2;  
   }  
   void func3() {  
      (funcArray[0])();   // C2064  
      (this->*funcArray[0])(); // OK - called in this instance context  
   }  
};  
```