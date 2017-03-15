---
title: "Исключение bad_cast | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "bad_cast"
  - "bad_cast_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_cast - ключевое слово [C++]"
  - "исключения, bad_cast"
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Исключение bad_cast
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Исключение `bad_cast` создается оператором `dynamic_cast` в результате ошибки приведения к ссылочному типу.  
  
## Синтаксис  
  
```  
catch (bad_cast)  
   statement  
```  
  
## Заметки  
 Исключение `bad_cast` имеет следующий интерфейс:  
  
```  
class bad_cast : public exception {  
public:  
   bad_cast(const char * _Message = "bad cast");  
   bad_cast(const bad_cast &);  
   virtual ~bad_cast();  
};  
```  
  
 Ниже приводится пример ошибки оператора `dynamic_cast`, при котором создается исключение `bad_cast`.  
  
```  
// expre_bad_cast_Exception.cpp  
// compile with: /EHsc /GR  
#include <typeinfo.h>  
#include <iostream>  
  
class Shape {  
public:  
   virtual void virtualfunc() const {}  
};  
  
class Circle: public Shape {  
public:  
   virtual void virtualfunc() const {}  
};  
  
using namespace std;  
int main() {  
   Shape shape_instance;  
   Shape& ref_shape = shape_instance;  
   try {  
      Circle& ref_circle = dynamic_cast<Circle&>(ref_shape);   
   }  
   catch (bad_cast b) {  
      cout << "Caught: " << b.what();  
   }  
}  
```  
  
 Исключение создается потому, что объект, для которого выполняется приведение \(Shape\), не является производным от указанного типа приведения \(Circle\).  Чтобы исключение не создавалось, добавьте в функцию `main` следующие объявления:  
  
```  
Circle circle_instance;  
Circle& ref_circle = circle_instance;  
```  
  
 Затем измените приведение в блоке `try` следующим образом:  
  
```  
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);  
```  
  
## См. также  
 [Оператор dynamic\_cast](../cpp/dynamic-cast-operator.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Обработка исключений С\+\+](../cpp/cpp-exception-handling.md)