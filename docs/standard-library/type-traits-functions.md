---
title: Функции &lt;type_traits&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- type_traits/std::is_assignable
- type_traits/std::is_copy_assignable
- type_traits/std::is_copy_constructible
- type_traits/std::is_default_constructible
- type_traits/std::is_move_assignable
- type_traits/std::is_move_constructible
- type_traits/std::is_nothrow_move_assignable
- type_traits/std::is_trivially_copy_assignable
- type_traits/std::is_trivially_move_assignable
- type_traits/std::is_trivially_move_constructible
ms.assetid: dce4492f-f3e4-4d5e-bdb4-5875321254ec
helpviewer_keywords:
- std::is_assignable
- std::is_copy_assignable
- std::is_copy_constructible
- std::is_default_constructible
- std::is_move_assignable
- std::is_move_constructible
- std::is_nothrow_move_assignable
- std::is_trivially_copy_assignable
- std::is_trivially_move_assignable
- std::is_trivially_move_constructible
ms.openlocfilehash: ff6d6066d90fe5049b89586ce657e62860c12f9f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861098"
---
# <a name="lttypetraitsgt-functions"></a>Функции &lt;type_traits&gt;

||||
|-|-|-|
|[is_assignable](#is_assignable)|[is_copy_assignable](#is_copy_assignable)|[is_copy_constructible](#is_copy_constructible)|
|[is_default_constructible](#is_default_constructible)|[is_move_assignable](#is_move_assignable)|[is_move_constructible](#is_move_constructible)|
|[is_nothrow_move_assignable](#is_nothrow_move_assignable)|[is_trivially_copy_assignable](#is_trivially_copy_assignable)|[is_trivially_move_assignable](#is_trivially_move_assignable)|
|[is_trivially_move_constructible](#is_trivially_move_constructible)|

## <a name="is_assignable"></a>  is_assignable

Проверяет, можно ли назначить значение типа `From` типу `To`.

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Параметры

Тип объекта, который получает назначение.

От типа объекта, который предоставляет значение.

### <a name="remarks"></a>Примечания

Невычисленное выражение `declval<To>() = declval<From>()` должно иметь правильный формат. `From` и `To` должны быть полными типами, `void`, или массивами с неизвестной границей.

## <a name="is_copy_assignable"></a>  is_copy_assignable

Проверяет, может ли тип быть скопирован при присвоении значения.

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>Параметры

`Ty` Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип `Ty` является классом, имеющим оператор присваивания копированием, в противном случае — значение false. Эквивалентно is_assignable\<Ty&, const Ty&>.

## <a name="is_copy_constructible"></a>  is_copy_constructible

Проверяет, есть ли у типа конструктор копии.

```cpp
template <class Ty>
struct is_copy_constructible;
```

### <a name="parameters"></a>Параметры

`Ty` Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип `Ty` является классом, имеющим конструктор копии, в противном случае — значение false.

### <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

struct Copyable
{
    int val;
};

struct NotCopyable
{
   NotCopyable(const NotCopyable&) = delete;
   int val;

};

int main()
{
    std::cout << "is_copy_constructible<Copyable> == " << std::boolalpha
        << std::is_copy_constructible<Copyable>::value << std::endl;
    std::cout << "is_copy_constructible<NotCopyable> == " << std::boolalpha
        << std::is_copy_constructible<NotCopyable>::value << std::endl;

    return (0);
}

```

```Output
is_copy_constructible<Copyable> == true
is_copy_constructible<NotCopyable > == false
```

## <a name="is_default_constructible"></a>  is_default_constructible

Проверяет, есть ли у типа конструктор по умолчанию.

```cpp
template <class Ty>
struct is_default_constructible;
```

### <a name="parameters"></a>Параметры

`T` Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Экземпляр предиката типа имеет значение true, если тип `T` является типом класса, имеющим конструктор по умолчанию, в противном случае — значение false. Это эквивалентно предикату `is_constructible<T>`. Тип `T` должен быть полным типом, `void`или массивом с неизвестными границами.

### <a name="example"></a>Пример

```cpp
#include <type_traits>
#include <iostream>

struct Simple
{
    Simple() : val(0) {}
    int val;
};

struct Simple2
{
    Simple2(int v) : val(v) {}
    int val;
};

int main()
{
    std::cout << "is_default_constructible<Simple> == " << std::boolalpha
        << std::is_default_constructible<Simple>::value << std::endl;
    std::cout << "is_default_constructible<Simple2> == " << std::boolalpha
        << std::is_default_constructible<Simple2>::value << std::endl;

    return (0);
}

```

```Output
is_default_constructible<Simple> == true
is_default_constructible<Simple2> == false
```

## <a name="is_move_assignable"></a>  is_move_assignable

Проверяет, является ли тип перемещаемым при присваивании.

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Параметры

`T` Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Тип является тип присваиваемым при перемещении, если ссылку rvalue на тип можно присвоить ссылке на тип. Предикат типа эквивалентен `is_assignable<T&, T&&>`. Перемещаемые при присваивании типы включают ссылочные скалярные типы и типы классов, в которых есть созданные компилятором или определяемые пользователем операторы присваивания.

## <a name="is_move_constructible"></a>  is_move_constructible

Проверяет, имеет ли тип конструктор перемещения.

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Параметры

T тип для вычисления

### <a name="remarks"></a>Примечания

Предикат типа, результатом вычисления которого будет значение true, если тип `T` может быть создан с помощью операции перемещения. Этот предикат эквивалентен `is_constructible<T, T&&>`.

## <a name="is_nothrow_move_assignable"></a>  is_nothrow_move_assignable

Проверяет, имеет ли тип оператор присваивания перемещения **nothrow**.

```cpp
template <class Ty>
struct is_nothrow_move_assignable;
```

### <a name="parameters"></a>Параметры

`Ty` Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип `Ty` имеет оператор присваивания перемещения nothrow; в противном случае — значение false.

## <a name="is_trivially_copy_assignable"></a>  is_trivially_copy_assignable

Проверяет, есть ли у типа тривиальный оператор присваивания копии.

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>Параметры

`T` Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип `T` является классом, имеющим тривиальный оператор присваивания копии, в противном случае — значение false.

Конструктор присваивания для класса `T` является тривиальным, если он предоставляется неявно, класс `T` не имеет виртуальных функций, класс `T` не имеет виртуальных базовых классов; классы для всех нестатических членов класса типа "класс" имеют тривиальные операторы присваивания, классы для всех нестатических членов типа "массив" также имеют тривиальные операторы присваивания.

## <a name="is_trivially_move_assignable"></a>  is_trivially_move_assignable

Проверяет, есть ли у типа тривиальный оператор присваивания перемещением.

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>Параметры

`Ty` Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип `Ty` является классом, имеющим тривиальный оператор присваивания перемещением, в противном случае — значение false.

Оператор присваивания перемещением для класса `Ty`, является тривиальным, если:

он неявно предоставляется;

класс `Ty` не имеет виртуальных функций;

класс `Ty` не имеет виртуальных баз;

классы всех нестатических элементов данных типа класса имеют тривиальные операторы присваивания перемещением;

классы всех нестатических элементов данных массива типов класса имеют тривиальные операторы присваивания перемещением.

## <a name="is_trivially_move_constructible"></a>  is_trivially_move_constructible

Проверяет, есть ли у типа тривиальный конструктор перемещения.

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>Параметры

`Ty` Запрашиваемый тип.

### <a name="remarks"></a>Примечания

Экземпляр предиката типа содержит значение true, если тип `Ty` является классом, имеющим тривиальный конструктор перемещения, в противном случае — значение false.

Конструктор перемещения для класса `Ty` является тривиальным, если:

он неявно объявлен;

его типы параметров эквивалентны типам неявного объявления;

класс `Ty` не имеет виртуальных функций;

класс `Ty` не имеет виртуальных баз;

класс не содержит изменчивых нестатических элементов данных;

все прямые базы класса `Ty` имеют тривиальные конструкторы перемещения;

классы всех нестатических элементов данных типа класса имеют тривиальные конструкторы перемещения;

классы всех нестатических элементов данных массива типов класса имеют тривиальные конструкторы перемещения.

## <a name="see-also"></a>См. также

[<type_traits>](../standard-library/type-traits.md)<br/>
