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
ms.openlocfilehash: b50995ff1d5eb730bf6593679194d32d5300b9d7
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944160"
---
# <a name="badcast-exception"></a>Исключение bad_cast
Исключение `bad_cast` создается оператором `dynamic_cast` в результате ошибки приведения к ссылочному типу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
catch (bad_cast)  
   statement  
```  
  
## <a name="remarks"></a>Примечания  
 Исключение `bad_cast` имеет следующий интерфейс:  
  
```cpp 
class bad_cast : public exception {  
public:  
   bad_cast(const char * _Message = "bad cast");  
   bad_cast(const bad_cast &);  
   virtual ~bad_cast();  
};  
```  
  
 Ниже приводится пример ошибки оператора `dynamic_cast`, при котором создается исключение `bad_cast`.  
  
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
  
 Исключение создается потому, что объект, для которого выполняется приведение (Shape), не является производным от указанного типа приведения (Circle). Чтобы избежать исключения, добавьте следующие объявления для **основной**:  
  
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