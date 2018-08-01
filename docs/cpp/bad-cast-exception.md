---
title: Исключение bad_cast | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- bad_cast
- bad_cast_cpp
dev_langs:
- C++
helpviewer_keywords:
- exceptions [C++], bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a37ae011ec2f06a505063678f481e6e41696c86
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401371"
---
# <a name="badcast-exception"></a>Исключение bad_cast
**Bad_cast** исключение **dynamic_cast** оператор, в результате ошибки приведения к ссылочному типу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
catch (bad_cast)  
   statement  
```  
  
## <a name="remarks"></a>Примечания  
 Интерфейс для **bad_cast** является:  
  
```cpp 
class bad_cast : public exception {  
public:  
   bad_cast(const char * _Message = "bad cast");  
   bad_cast(const bad_cast &);  
   virtual ~bad_cast();  
};  
```  
  
 Следующий код содержит пример ошибки оператора **dynamic_cast** , порождающий **bad_cast** исключение.  
  
```cpp 
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
  
 Исключение создается потому, что объект, для которого выполняется приведение (Shape), не является производным от указанного типа приведения (Circle). Чтобы исключение не создавалось, добавьте в функцию `main` следующие объявления:  
  
```cpp 
Circle circle_instance;  
Circle& ref_circle = circle_instance;  
```  
  
 Затем измените приведение в **попробуйте** блокировать следующим образом:  
  
```cpp 
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);  
```  
  
## <a name="see-also"></a>См. также  
 [Оператор dynamic_cast](../cpp/dynamic-cast-operator.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Обработка исключений С++](../cpp/cpp-exception-handling.md)