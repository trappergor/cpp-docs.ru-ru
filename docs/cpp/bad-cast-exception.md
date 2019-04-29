---
title: Исключение bad_cast
ms.date: 11/04/2016
f1_keywords:
- bad_cast
- bad_cast_cpp
helpviewer_keywords:
- exceptions [C++], bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
ms.openlocfilehash: 028fa8cc90b33aca6a37fb3b7f58b8c5fad81bd7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62284777"
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

[Оператор dynamic_cast](../cpp/dynamic-cast-operator.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Обработка исключений С++](../cpp/cpp-exception-handling.md)