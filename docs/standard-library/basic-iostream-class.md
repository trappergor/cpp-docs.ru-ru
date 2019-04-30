---
title: Класс basic_iostream
ms.date: 11/04/2016
f1_keywords:
- istream/std::basic_iostream
- istream/std::basic_iostream::swap
helpviewer_keywords:
- basic_iostream class
ms.assetid: 294b680b-eb49-4066-8db2-6d52dac9d6e3
ms.openlocfilehash: 80aad69f05b7473b508447d6f69f1d92edbeeca3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400647"
---
# <a name="basiciostream-class"></a>Класс basic_iostream

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

## <a name="remarks"></a>Примечания

Этот класс шаблона описывает объект, управляющий вставками с помощью базового класса [basic_ostream](../standard-library/basic-ostream-class.md)< `Elem`, `Tr`> и извлечениями с помощью базового класса [basic_istream](../standard-library/basic-istream-class.md)< `Elem`, `Tr`>. У этих двух объектов общий виртуальный базовый класс [basic_ios](../standard-library/basic-ios-class.md)< `Elem`, `Tr`>. Они также управляют общим буфером потока с элементами типа `Elem`, признаки символов которых определяются классом `Tr`. Конструктор инициализирует базовые классы с помощью `basic_istream`( **strbuf**) и `basic_ostream`( **strbuf**).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_iostream](#basic_iostream)|Создание объекта `basic_iostream`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[swap](#swap)|Меняет местами содержимое предоставленного объекта `basic_iostream` на содержимое этого объекта.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
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

*strbuf*<br/>
Существующий объект `basic_streambuf`.

*right*<br/>
Существующий объект `basic_iostream`, который используется для создания нового объекта `basic_iostream`.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует базовые объекты посредством `basic_istream(strbuf)` и `basic_ostream(strbuf)`.

Второй конструктор инициализирует базовые объекты путем вызова `move(right)`.

## <a name="op_eq"></a>  basic_iostream::operator=

Присваивает значение указанного объекта `basic_iostream` этому объекту. Это назначение перемещения, включающее rvalue, которое не оставляет копию.

```cpp
basic_iostream& operator=(basic_iostream&& right);
```

### <a name="parameters"></a>Параметры

*right*<br/>
Ссылка `rvalue` на объект `basic_iostream`, на основе которого будет присвоено значение.

### <a name="remarks"></a>Примечания

Оператор-член вызывает `swap(right)`.

## <a name="swap"></a>  basic_iostream::swap

Меняет местами содержимое предоставленного объекта `basic_iostream` на содержимое этого объекта.

```cpp
void swap(basic_iostream& right);
```

### <a name="parameters"></a>Параметры

*right*<br/>
Объект `basic_iostream` для обмена.

### <a name="remarks"></a>Примечания

Функция-член вызывает `swap(right)`.

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
