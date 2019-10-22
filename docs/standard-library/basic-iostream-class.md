---
title: Класс basic_iostream
ms.date: 11/04/2016
f1_keywords:
- istream/std::basic_iostream
- istream/std::basic_iostream::swap
helpviewer_keywords:
- basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
ms.openlocfilehash: 190c9aa23493cea67bae44be93fd3fdbdecc4447
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72690007"
---
# <a name="basic_iostream-class"></a>Класс basic_iostream

Класс потока, поддерживающий ввод и вывод.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_iostream : public basic_istream<Elem, Tr>,
    public basic_ostream<Elem, Tr>
{
public:
    explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

    virtual ~basic_iostream();

};
```

## <a name="remarks"></a>Заметки

Шаблон класса описывает объект, управляющий вставками через его базовый класс [basic_ostream](../standard-library/basic-ostream-class.md) <  `Elem`, `Tr` > и извлечения, через его базовый класс [basic_istream](../standard-library/basic-istream-class.md) <  `Elem`, `Tr` >. У этих двух объектов общий виртуальный базовый класс [basic_ios](../standard-library/basic-ios-class.md)< `Elem`, `Tr`>. Они также управляют общим буфером потока с элементами типа `Elem`, признаки символов которых определяются классом `Tr`. Конструктор инициализирует базовые классы с помощью `basic_istream`( **strbuf**) и `basic_ostream`( **strbuf**).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_iostream](#basic_iostream)|Создание объекта `basic_iostream`.|

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
|-|-|
|[swap](#swap)|Меняет местами содержимое предоставленного объекта `basic_iostream` на содержимое этого объекта.|

### <a name="operators"></a>Операторы

|оператора|Описание|
|-|-|
|[оператор=](#op_eq)|Присваивает значение указанного объекта `basic_iostream` этому объекту. Это назначение перемещения, включающее `rvalue`, которое не оставляет копию.|

## <a name="requirements"></a>Требования

**Заголовок:** \<istream>

**Пространство имен:** std

## <a name="basic_iostream"></a>  basic_iostream::basic_iostream

Создание объекта `basic_iostream`.

```cpp
explicit basic_iostream(basic_streambuf<Elem, Tr>* strbuf);

basic_iostream(basic_iostream&& right);

basic_iostream();
```

### <a name="parameters"></a>Параметры

*strbuf* \
Существующий объект `basic_streambuf`.

*справа* \
Существующий объект `basic_iostream`, который используется для создания нового объекта `basic_iostream`.

### <a name="remarks"></a>Заметки

Первый конструктор инициализирует базовые объекты посредством `basic_istream(strbuf)` и `basic_ostream(strbuf)`.

Второй конструктор инициализирует базовые объекты, вызывая `move(right)`.

## <a name="op_eq"></a>  basic_iostream::operator=

Присваивает значение указанного объекта `basic_iostream` этому объекту. Это назначение перемещения, включающее rvalue, которое не оставляет копию.

```cpp
basic_iostream& operator=(basic_iostream&& right);
```

### <a name="parameters"></a>Параметры

*справа* \
Ссылка `rvalue` на объект `basic_iostream`, на основе которого будет присвоено значение.

### <a name="remarks"></a>Заметки

Оператор члена вызывает `swap(right)`.

## <a name="swap"></a>  basic_iostream::swap

Меняет местами содержимое предоставленного объекта `basic_iostream` на содержимое этого объекта.

```cpp
void swap(basic_iostream& right);
```

### <a name="parameters"></a>Параметры

*справа* \
Объект `basic_iostream` для обмена.

### <a name="remarks"></a>Заметки

Функция члена вызывает `swap(right)`.

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostreams](../standard-library/iostreams-conventions.md)
