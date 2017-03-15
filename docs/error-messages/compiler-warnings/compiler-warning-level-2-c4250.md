---
title: "Предупреждение компилятора (уровень 2) C4250 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4250"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4250"
ms.assetid: d47f7249-6b5a-414b-b2d4-56e5d246a782
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Предупреждение компилятора (уровень 2) C4250
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс 1" : наследуется "класс 2::член" через превосходство  
  
 Два или более членов имеют одинаковые имена.  Один член в `class2` наследуется, так как это базовый класс для других классов, содержащих этот член.  
  
 Для отключения предупреждения C4250 используйте директиву pragma [warning](../../preprocessor/warning.md).  
  
 Так как виртуальный базовый класс является общим для многочисленных производных классов, имя в производном классе превосходит имя в базовом классе.  Например, в следующей иерархии классов присутствуют два определения функции, унаследованной в рамках ромбовидной структуры: экземпляр vbc::func\(\) представлен в слабом классе, а экземпляр dominant::func\(\) представлен в доминирующем классе.  Вызов функции func\(\) без уточнения через объект класса ромбовидной структуры всегда приводит к выводу экземпляра dominate::func\(\).  Если слабый класс должен вывести экземпляр функции func\(\), никакое из определений не будет доминировать и вызов будет отмечен как неоднозначный.  
  
```  
// C4250.cpp  
// compile with: /c /W2  
#include <stdio.h>  
struct vbc {  
   virtual void func() { printf("vbc::func\n"); }  
};  
  
struct weak : public virtual vbc {};  
  
struct dominant : public virtual vbc {  
   void func() { printf("dominant::func\n"); }  
};  
  
struct diamond : public weak, public dominant {};  
  
int main() {  
   diamond d;  
   d.func();   // C4250  
}  
```  
  
## Пример  
 В следующем примере продемонстрировано возникновение ошибки C4250.  
  
```  
// C4250_b.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
using namespace std;  
class A {  
public:  
   virtual operator int () {  
      return 2;  
   }  
};  
  
class B : virtual public A {  
public:  
   virtual operator int () {  
      return 3;  
   }  
};  
  
class C : virtual public A {};  
  
class E : public B, public C {};   // C4250  
  
int main() {  
   E eObject;  
   cout << eObject.operator int() << endl;  
}  
```  
  
## Пример  
 В этом примере показана более сложная ситуация.  В следующем примере продемонстрировано возникновение ошибки C4250.  
  
```  
// C4250_c.cpp  
// compile with: /W2 /EHsc  
#include <iostream>  
using namespace std;  
  
class V {  
public:  
   virtual int f() {  
      return 1024;  
   }  
};  
  
class B : virtual public V {  
public:  
   int b() {  
      return f(); // B::b() calls V::f()  
   }  
};  
  
class M : virtual public V {  
public:  
   int f() {  
      return 7;  
   }  
};  
  
// because of dominance, f() is M::f() inside D,  
// changing the meaning of B::b's f() call inside a D  
class D : public B, public M {};   // C4250  
  
int main() {  
   D d;  
   cout << "value is: " << d.b();   // invokes M::f()  
}  
```