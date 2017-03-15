---
title: "Ошибка компилятора C2248 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2248"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2248"
ms.assetid: 7a3ba0e8-d3b9-4bb9-95db-81ef17e31d23
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Ошибка компилятора C2248
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"член": невозможно обратиться к члену "уровень доступа", объявленному в классе "класс"  
  
 Члены производного класса не могут обращаться к членам `private` базового класса.  Обращение к членам `private` или `protected` экземпляров класса невозможно.  
  
 Дополнительные сведения об ошибке C2248 см. в статье KB243351 базы знаний.  
  
 Следующий пример приводит к возникновению ошибки C2248:  
  
```  
// C2248.cpp  
#include <stdio.h>  
class X {  
public:  
   int  m_pubMemb;  
   void setPrivMemb( int i ) {  
      m_privMemb = i;  
      printf_s("\n%d", m_privMemb);  
   }  
protected:  
   int  m_protMemb;  
  
private:  
   int  m_privMemb;  
} x;  
  
int main() {  
   x.m_pubMemb = 4;  
   printf_s("\n%d", x.m_pubMemb);  
   x.m_protMemb = 2;   // C2248 m_protMemb is protected  
   x.m_privMemb = 3;   // C2248  m_privMemb is private  
   x.setPrivMemb(0);   // OK uses public access function  
}  
```  
  
 Возникновение ошибки C2248 также может быть связано с проблемами совместимости при использовании дружественных шаблонов и специализации.  Дополнительные сведения см. в разделе [Ошибка компоновщика LNK2019](../Topic/Linker%20Tools%20Error%20LNK2019.md).  
  
```  
// C2248_b.cpp  
template<class T>  
void f(T t) {  
   t.i;   // C2248  
}  
  
struct S {  
private:  
   int i;  
  
public:  
   S() {}  
   // Delete the following line to resolve.  
   friend void f(S);   // refer to the non-template function void f(S)  
  
   // Uncomment the following line to resolve.  
   // friend void f<S>(S);  
};  
  
int main() {  
   S s;  
   f<S>(s);  
}  
```  
  
 Ошибка C2248 также может быть связана с проблемами совместимости, которые возникают при попытке объявления дружественного класса, если включающий класс находится за пределами видимости объявления дружественного класса в области действия класса.  Чтобы устранить ошибку, следует предоставить статус дружественного включающему классу.  
  
```  
// C2248_c.cpp  
// compile with: /c  
class T {  
   class S {  
      class E {};  
   };  
   friend class S::E;   // C2248  
};  
  
class A {  
   class S {  
      class E {};  
      friend class A;   // grant friendship to enclosing class  
   };  
   friend class S::E;   // OK  
};  
```