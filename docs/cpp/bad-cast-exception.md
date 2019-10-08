---
title: Исключение bad_cast
ms.date: 10/04/2019
f1_keywords:
- bad_cast
- bad_cast_cpp
helpviewer_keywords:
- exceptions [C++], bad_cast
- bad_cast keyword [C++]
ms.assetid: 31eae1e7-d8d5-40a0-9fef-64a6a4fc9021
ms.openlocfilehash: 7384394fb53c6aa4bc009a903ba0ed22bf0ed0d6
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998773"
---
# <a name="bad_cast-exception"></a>Исключение bad_cast

Исключение **bad_cast** создается оператором **dynamic_cast** в качестве результата неудачного приведения к ссылочному типу.

## <a name="syntax"></a>Синтаксис

```
catch (bad_cast)
   statement
```

## <a name="remarks"></a>Примечания

Интерфейс для **bad_cast** :

```cpp
class bad_cast : public exception
```

Следующий код содержит пример неудачного **dynamic_cast** , который вызывает исключение **bad_cast** .

```cpp
// expre_bad_cast_Exception.cpp
// compile with: /EHsc /GR
#include <typeinfo>
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

Исключение возникает, так как объект, который поддается (Shape), не является производным от указанного типа приведения (Circle). Чтобы исключение не создавалось, добавьте в функцию `main` следующие объявления:

```cpp
Circle circle_instance;
Circle& ref_circle = circle_instance;
```

Затем измените смысл приведения в блоке **try** следующим образом:

```cpp
Shape& ref_shape = dynamic_cast<Shape&>(ref_circle);
```

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[bad_cast](#bad_cast)|Конструктор для объектов типа `bad_cast`.|

### <a name="functions"></a>Функции

|Функция|Описание|
|-|-|
|[What](#what)|TBD|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор=](#op_eq)|Оператор присваивания, который присваивает один объект `bad_cast` другому.|

## <a name="bad_cast"></a>bad_cast

Конструктор для объектов типа `bad_cast`.

```cpp
bad_cast(const char * _Message = "bad cast");
bad_cast(const bad_cast &);
```

## <a name="op_eq"></a>Оператор =

Оператор присваивания, который присваивает один объект `bad_cast` другому.

```cpp
bad_cast& operator=(const bad_cast&) noexcept;
```

## <a name="what"></a>What

```cpp
const char* what() const noexcept override;
```

## <a name="see-also"></a>См. также

[оператор dynamic_cast](../cpp/dynamic-cast-operator.md)\
[Ключевые слова](../cpp/keywords-cpp.md)\
[Обработка исключений С++](../cpp/cpp-exception-handling.md)
