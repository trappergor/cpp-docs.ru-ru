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
ms.openlocfilehash: b40f64671e7c259b7dc04b31a11d20d0fc76c5c4
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68242397"
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
class bad_cast : public exception
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

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[bad_cast](#bad_cast)|Конструктор для объектов типа `bad_cast`.|

### <a name="functions"></a>Функции

|Функция|Описание|
|-|-|
|[что](#what)|TBD|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор=](#op_eq)|Оператор присваивания, который назначает один `bad_cast` объект с другим объектом.|

## <a name="bad_cast"></a> bad_cast

Конструктор для объектов типа `bad_cast`.

```cpp
bad_cast(const char * _Message = "bad cast");
bad_cast(const bad_cast &);
```

## <a name="op_eq"></a> оператор =

Оператор присваивания, который назначает один `bad_cast` объект с другим объектом.

```cpp
bad_cast& operator=(const bad_cast&) noexcept;
```

## <a name="what"></a> что

```cpp
const char* what() const noexcept override;
```

## <a name="see-also"></a>См. также

[Оператор dynamic_cast](../cpp/dynamic-cast-operator.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)<br/>
[Обработка исключений С++](../cpp/cpp-exception-handling.md)