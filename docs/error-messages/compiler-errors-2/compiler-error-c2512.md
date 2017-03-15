---
title: "Ошибка компилятора C2512 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2512"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2512"
ms.assetid: 15206da9-1164-451a-b869-280e00711aad
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2512
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

identifier: нет подходящего конструктора по умолчанию  
  
 Нет конструктора по умолчанию для указанного класса, структуры или объединения.  Компилятор предоставляет конструктор по умолчанию только в том случае, если не указаны пользовательские конструкторы.  
  
 Если вы предоставляете конструктор, принимающий отличный от void параметр, и хотите разрешить создание класса без параметров, например в качестве элементов массива, необходимо также указать конструктор по умолчанию.  Конструктор по умолчанию может быть конструктором со значениями по умолчанию для всех параметров.  
  
 В следующем примере показано возникновение ошибки C2512 и приводятся сведения по ее устранению.  
  
```  
// C2512.cpp  
// C2512 expected  
struct B {  
   B (char *);  
   // Uncomment the following line to fix.  
   // B() {};  
};  
  
int main() {  
   B b;   
}  
```  
  
 Ниже приведен пример менее явной ошибки C2512.  Для устранения этой ошибки измените код, чтобы определить класс до ссылки на его конструктор:  
  
```  
// C2512b.cpp  
// compile with: /c  
struct S {  
   struct X;  
  
   void f() {  
      X *x = new X();   // C2512 X not defined yet  
   }  
  
};  
  
struct S::X {};  
  
struct T {  
   struct X;  
   void f();  
};  
  
struct T::X {};  
  
void T::f() {  
   X *x = new X();  
}  
```  
  
 Причиной ошибки C2512 также может быть вызов для создания класса, содержащего константный член или член ссылочных данных.  Эти члены должны быть инициализированы в списке инициализаторов конструктора, который не позволяет компилятору создать конструктор по умолчанию.  
  
 В следующем примере показано возникновение ошибки C2512 и приводятся сведения по ее устранению.  
  
```  
// C2512c.cpp  
// Compile by using: cl /c /W3 C2512c.cpp  
struct S {  
   const int i_;  
   int &r_;   
};   
  
int SumS() {  
   const int ci = 7;  
   int ir = 42;  
  
   S s1; // C2512 - no default constructor available  
   S s2{ci, ir};  // Fix - initialize const and reference members   
   return s2.i_ + s2.r_;  
}  
```