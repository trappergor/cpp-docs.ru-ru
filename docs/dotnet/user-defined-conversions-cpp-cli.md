---
title: "заданные пользователем преобразования (C++/CLI) | Microsoft Docs"
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
  - "заданные пользователем преобразования [C++]"
ms.assetid: 8010fd59-2775-4e9a-a6ed-58055032d66f
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# заданные пользователем преобразования (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этом разделе обсуждаются определенное пользователем преобразование \(UDC\), когда один из типов преобразование ссылку или экземпляр типа значения или ссылочного типа.  
  
## Явное и неявное преобразование  
 Определенное пользователем преобразование может быть неявным или точно.  UDC должен быть неявный при преобразовании не приводит к потере данных.  В противном случае точный UDC обязательно.  
  
 Конструктор собственного класса можно использовать, чтобы преобразовать ссылку или тип значения к собственному классу.  
  
 Дополнительные сведения о преобразованиях см. в разделе [Упаковка\-преобразование](../windows/boxing-cpp-component-extensions.md) и [Стандартные преобразования](../cpp/standard-conversions.md).  
  
```  
// mcpp_User_Defined_Conversions.cpp  
// compile with: /clr  
#include "stdio.h"  
ref class R;  
class N;  
  
value class V {  
   static operator V(R^) {  
      return V();  
   }  
};  
  
ref class R {  
public:  
   static operator N(R^);  
   static operator V(R^) {  
      System::Console::WriteLine("in R::operator N");  
      return V();  
   }  
};  
  
class N {  
public:  
   N(R^) {  
      printf("in N::N\n");  
   }  
};  
  
R::operator N(R^) {  
   System::Console::WriteLine("in R::operator N");  
   return N(nullptr);  
}  
  
int main() {  
   // Direct initialization:  
   R ^r2;  
   N n2(r2);   // direct initialization, calls constructor  
   static_cast<N>(r2);   // also direct initialization  
  
   R ^r3;  
   // ambiguous V::operator V(R^) and R::operator V(R^)  
   // static_cast<V>(r3);     
}  
```  
  
 **Output**  
  
  **в N::N**  
**в N::N**   
## Новообращенный\-от операторов  
 Новообращенный\- от операторов создайте объект класса, в котором определен оператор из объекта какого\-либо другого класса.  
  
 В стандартном языке C — C\+\+ не поддерживает новообращенный\- от операторов; в стандартном языке C — C\+\+ используются конструкторы для этой цели.  Однако при использовании типов среды CLR, Visual C\+\+ синтактную предоставляет поддержку для вызова новообращенный\- от операторов.  
  
 Чтобы правильно взаимодействовать с другими cls\-совместимыми языками, может потребоваться создать каждый определенный пользователем унарный конструктор для данного класса с соответствовать новообращенный\- от оператора.  
  
 Новообращенный\-от операторов:  
  
-   Определяет как статические функции.  
  
-   Может быть неявный \(для преобразований, не теряют точность, например коротк\-к\- int\) или неточным, когда могут быть потеря точности.  
  
-   Возвращает объект содержащего класса.  
  
-   Содержит «из» типа1 только как тип параметра.  
  
 В следующем примере показано неявное и явный «новообращенный\- от», оператор \(UDC\) определенное пользователем преобразование.  
  
```  
// clr_udc_convert_from.cpp  
// compile with: /clr  
value struct MyDouble {  
   double d;  
  
   MyDouble(int i) {  
      d = static_cast<double>(i);  
      System::Console::WriteLine("in constructor");  
   }  
  
   // Wrap the constructor with a convert-from operator.  
   // implicit UDC because conversion cannot lose precision  
   static operator MyDouble (int i) {  
      System::Console::WriteLine("in operator");  
      // call the constructor  
      MyDouble d(i);  
      return d;  
   }  
  
   // an explicit user-defined conversion operator  
   static explicit operator signed short int (MyDouble) {  
      return 1;  
   }  
};  
  
int main() {  
   int i = 10;  
   MyDouble md = i;  
   System::Console::WriteLine(md.d);  
  
   // using explicit user-defined conversion operator requires a cast    
   unsigned short int j = static_cast<unsigned short int>(md);  
   System::Console::WriteLine(j);  
}  
```  
  
 **Output**  
  
  **в операторе**  
**Конструктор in**  
**10**  
**1**   
## Новообращенный\- к операторов  
 Новообращенный\- к операторам преобразование объекта класса, в котором определен оператор какому\-либо другому объекту.  В следующем примере показано неявное, новообращенный\- к, оператор определенное пользователем преобразование:  
  
```  
// clr_udc_convert_to.cpp  
// compile with: /clr  
using namespace System;  
value struct MyInt {  
   Int32 i;  
  
   // convert MyInt to String^  
   static operator String^ ( MyInt val ) {  
      return val.i.ToString();  
   }  
  
   MyInt(int _i) : i(_i) {}  
};  
  
int main() {  
   MyInt mi(10);  
   String ^s = mi;  
   Console::WriteLine(s);  
}  
```  
  
 **Output**  
  
  **10** Точное определенное пользователем новообращенный\- к оператора преобразования подходит для преобразований, потенциально теряют данные каким\-либо образом.  Чтобы вызвать явную новообращенный\- к оператора, приведение не требуется использовать.  
  
```  
// clr_udc_convert_to_2.cpp  
// compile with: /clr  
value struct MyDouble {  
   double d;  
   // convert MyDouble to Int32  
   static explicit operator System::Int32 ( MyDouble val ) {  
      return (int)val.d;  
   }  
};  
  
int main() {  
   MyDouble d;  
   d.d = 10.3;  
   System::Console::WriteLine(d.d);  
   int i = 0;  
   i = static_cast<int>(d);  
   System::Console::WriteLine(i);  
}  
```  
  
 **Output**  
  
  **10.3**  
**10**   
## Преобразование универсальные классы  
 Можно преобразовать универсальный класс в T.  
  
```  
// clr_udc_generics.cpp  
// compile with: /clr  
generic<class T>   
public value struct V {  
   T mem;  
   static operator T(V v) {  
      return v.mem;  
   }  
  
   void f(T t) {  
      mem = t;  
   }  
};  
  
int main() {  
   V<int> v;  
   v.f(42);  
   int i = v;  
   i += v;  
   System::Console::WriteLine(i == (42 * 2) );  
}  
```  
  
 **Output**  
  
  **True** При преобразовании конструктор получает тип и использует его для создания объекта.  Вызывается при преобразовании конструктор напрямую с инициализацией только; приведение не призовут преобразования конструкторы.  По умолчанию преобразование конструкторы явным образом для типов CLR.  
  
```  
// clr_udc_converting_constructors.cpp  
// compile with: /clr  
public ref struct R {  
   int m;  
   char c;  
  
   R(int i) : m(i) { }  
   R(char j) : c(j) { }  
};  
  
public value struct V {  
   R^ ptr;  
   int m;  
  
   V(R^ r) : ptr(r) { }  
   V(int i) : m(i) { }  
};  
  
int main() {   
   R^ r = gcnew R(5);  
  
   System::Console::WriteLine( V(5).m);  
   System::Console::WriteLine( V(r).ptr);  
}  
```  
  
 **Output**  
  
  **5**  
**R** В этом примере кода, неявная статическую функцию преобразования выполняются те же действия, как конструктор явного преобразования.  
  
```  
public value struct V {  
   int m;  
   V(int i) : m(i) {}  
   static operator V(int i) {  
      V v(i*100);  
      return v;  
   }  
};  
  
public ref struct R {  
   int m;  
   R(int i) : m(i) {}  
   static operator R^(int i) {  
      return gcnew R(i*100);  
   }  
};  
  
int main() {  
   V v(13);   // explicit  
   R^ r = gcnew R(12);   // explicit  
  
   System::Console::WriteLine(v.m);  
   System::Console::WriteLine(r->m);  
  
   // explicit ctor can't be called here: not ambiguous  
   v = 5;  
   r = 20;  
  
   System::Console::WriteLine(v.m);  
   System::Console::WriteLine(r->m);  
}  
```  
  
 **Output**  
  
  **13**  
**12**  
**500**  
**2000**   
## См. также  
 [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)