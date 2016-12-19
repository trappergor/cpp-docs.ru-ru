---
title: "Ошибка компилятора C2327 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2327"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2327"
ms.assetid: 95278c95-d1f9-4487-ad27-53311f5e8112
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2327
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"символ" : не является именем типа, статическим членом или перечислителем  
  
 Код во вложенном классе пытается обратиться к элементу включающего класса, не являющемуся именем типа, статическим членом или перечислителем.  
  
 При компиляции с параметром **\/clr** наиболее распространенная причина появления ошибки C2327 состоит в том, что свойство имеет то же имя, что и тип свойства.  
  
 Следующий пример приводит к возникновению ошибки C2327:  
  
```  
// C2327.cpp  
int x;  
class enclose {  
public:  
   int x;  
   static int s;  
   class inner {  
      void f() {  
         x = 1;   // C2327; enclose::x is not static  
         s = 1;   // ok; enclose::s is static  
         ::x = 1;   // ok; ::x refers to global  
      }  
   };  
};  
```  
  
 Ошибка C2327 может также возникать в случае, когда имя типа скрыто именем члена класса:  
  
```  
// C2327b.cpp  
class X {};  
  
class S {  
   X X;  
   // try the following line instead  
   // X MyX;  
   X other;   // C2327, rename member X  
};  
```  
  
 Ошибка C2327 также возникает в ситуации, в которой требуется полностью указывать тип данных параметра:  
  
```  
// C2327c.cpp  
// compile with: /c  
struct A {};  
  
struct B {  
   int A;  
   void f(A a) {   // C2327  
   void f2(struct A a) {}   // OK  
   }  
};  
```  
  
 Следующий пример приводит к возникновению ошибки C2327:  
  
```  
// C2327d.cpp  
// compile with: /clr /c  
using namespace System;  
  
namespace NA {  
   public enum class E : Int32 {  
      one = 1,  
      two = 2,  
      three = 3  
   };  
  
   public ref class A {  
   private:  
      E m_e;  
   public:  
      property E E {  
         NA::E get() {  
            return m_e;  
         }  
         // At set, compiler doesn't know whether E is get_E or   
         // Enum E, therefore fully qualifying Enum E is necessary  
         void set( E e ) {   // C2327  
            // try the following line instead  
            // void set(NA::E e) {  
            m_e = e;  
         }  
      }  
   };  
}  
```  
  
 Ошибка C2327 может также возникать при использовании управляемых расширений для C\+\+:  
  
```  
// C2327e.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
namespace NA {  
   public __value enum E : Int32 {  
      one = 1, two = 2, three = 3  
   };  
  
   public __gc class A {  
      E m_e;  
      public:  
         __property E get_E() {  
            return m_e;  
         }  
         // At set_E compiler doesn't know whether E is get_E or   
         // Enum E, therefore fully qualifying Enum E is necessary  
         __property void set_E(E e) {   // C2327  
         // try the following line instead  
         // __property void set_E(NA::E e) {  
            m_e = e;  
         }  
   };  
}  
```  
  
 В следующем примере показано возникновение ошибки C2327 в случае, когда свойство имеет то же имя, что и тип свойства:  
  
```  
// C2327f.cpp  
// compile with: /clr /c  
public value class Address {};  
  
public ref class Person {  
public:  
   property Address Address {  
      ::Address get() {     
         return address;  
      }  
      void set(Address addr) {   // C2327  
      // try the following line instead  
      // set(::Address addr) {  
         address = addr;   
      }  
   }  
private:  
   Address address;   // C2327  
   // try the following line instead  
   // ::Address address;  
};  
```  
  
 В следующем примере показано возникновение ошибки C2327 в случае, когда свойство имеет то же имя, что и тип свойства:  
  
```  
// C2327g.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
public __value struct Address {};  
  
public __gc class Person {  
public:  
   __property ::Address get_Address() {     
      return address;  
   }  
  
   __property void set_Address(Address addr)   // C2327  
   // try the following line instead  
   // __property void set_Address(::Address addr) {  
      address = addr;   
   }  
  
private:  
   Address address;   // C2327  
  
   // try the following line instead  
   // ::Address address;  
};  
```