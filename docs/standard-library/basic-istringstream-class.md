---
title: Класс basic_istringstream
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_istringstream
- sstream/std::basic_istringstream::allocator_type
- sstream/std::basic_istringstream::rdbuf
- sstream/std::basic_istringstream::str
- sstream/std::basic_istringstream::swap
helpviewer_keywords:
- std::basic_istringstream [C++]
- std::basic_istringstream [C++], allocator_type
- std::basic_istringstream [C++], rdbuf
- std::basic_istringstream [C++], str
- std::basic_istringstream [C++], swap
ms.assetid: 1d5bb4b5-793d-4833-98e5-14676c451915
ms.openlocfilehash: b88411316ae247499100a044a0a2dfb3c53bc84f
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689986"
---
# <a name="basic_istringstream-class"></a>Класс basic_istringstream

Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_istringstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>Параметры

@No__t_1 *выделения*
Класс распределителя.

*Elem* \
Тип основного элемента строки.

*Tr* \
Признаки символа, соответствующие основному элементу строки.

## <a name="remarks"></a>Заметки

Шаблон класса описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **Elem**, **tr**`Alloc` > с элементами типа *elem*, символом которых является признаки определяются классом *tr*, элементы которого выделяются распределителем класса *Alloc*. Объект сохраняет объект класса basic_stringbuf< **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_istringstream](#basic_istringstream)|Создает объект типа `basic_istringstream`.|

### <a name="typedefs"></a>Typedefs

|Имя типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Этот тип является синонимом для параметра шаблона `Alloc`.|

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
|-|-|
|[rdbuf](#rdbuf)|Возвращает адрес буфера сохраненного потока типа `pointer` в [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>.|
|[str](#str)|Задает или получает текст в буфере строк без изменения позиции записи.|
|[swap](#swap)|Меняет местами значения в этом объекте `basic_istringstream` и значения предоставленного объекта.|

### <a name="operators"></a>Операторы

|оператора|Описание|
|-|-|
|[оператор=](#op_eq)|Назначает значения этому объекту `basic_istringstream` из параметра объекта.|

## <a name="requirements"></a>Требования

**Заголовок:** \<sstream>

**Пространство имен:** std

## <a name="allocator_type"></a>  basic_istringstream::allocator_type

Этот тип является синонимом для параметра шаблона `Alloc`.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_istringstream"></a>  basic_istringstream::basic_istringstream

Создает объект типа `basic_istringstream`.

```cpp
explicit basic_istringstream(
    ios_base::openmode _Mode = ios_base::in);

explicit basic_istringstream(
    const basic_string<Elem, Tr, Alloc>& str,
    ios_base::openmode _Mode = ios_base::in);

basic_istringstream(
    basic_istringstream&& right);
```

### <a name="parameters"></a>Параметры

*_Mode* \
Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

\ *str*
Объект типа `basic_string`.

*справа* \
Ссылка rvalue на объект `basic_istringstream`.

### <a name="remarks"></a>Заметки

Первый конструктор инициализирует базовый класс путем вызова [basic_istream](../standard-library/basic-istream-class.md)(`sb`), где `sb` является сохраненным объектом класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md) <  `Elem`, `Tr`, `Alloc` >. Он также инициализирует `sb` путем вызова `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `_Mode` &#124; `ios_base::in`).

Второй конструктор инициализирует базовый класс путем вызова `basic_istream(sb)`. Он также инициализирует `sb` путем вызова `basic_stringbuf`< `Elem`, `Tr`, `Alloc`>( `str`, `_Mode` &#124; `ios_base::in`).

Третий конструктор инициализирует объект с содержимым *right*, который рассматривается как ссылка rvalue.

## <a name="op_eq"></a>  basic_istringstream::operator=

Назначает значения этому объекту `basic_istringstream` из параметра объекта.

```cpp
basic_istringstream& operator=(basic_istringstream&& right);
```

### <a name="parameters"></a>Параметры

*справа* \
Ссылка rvalue на объект `basic_istringstream`.

### <a name="remarks"></a>Заметки

Оператор Member заменяет содержимое объекта содержимым *right*, которое рассматривается как присваивание перемещения ссылки rvalue.

## <a name="rdbuf"></a>  basic_istringstream::rdbuf

Возвращает адрес буфера сохраненного потока типа `pointer` в [basic_stringbuf](../standard-library/basic-stringbuf-class.md) < **Elem**, **tr**`Alloc` >.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Возвращаемое значение

Адрес буфера сохраненного потока типа `pointer` для basic_stringbuf < **elem**, **tr**`Alloc` >.

### <a name="example"></a>Пример

Пример, в котором используется `rdbuf`, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="str"></a>  basic_istringstream::str

Задает или получает текст в буфере строк без изменения позиции записи.

```cpp
basic_string<Elem, Tr, Alloc> str() const;

void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Параметры

*_Newstr* \
Новая строка.

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект класса [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`>, управляемая последовательность которого является копией последовательности, управляемой **\*this**.

### <a name="remarks"></a>Заметки

Первая функция-член возвращает [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str). Вторая функция-член вызывает `rdbuf` -> **str**( `_Newstr`).

### <a name="example"></a>Пример

Пример, в котором используется `str`, см. в разделе [basic_stringbuf:: str](../standard-library/basic-stringbuf-class.md#str) .

## <a name="swap"></a>  basic_istringstream::swap

Меняет местами значения двух объектов `basic_istringstream`.

```cpp
void swap(basic_istringstream& right);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*right*|Ссылка `lvalue` на объект `basic_istringstream`.|

### <a name="remarks"></a>Заметки

Функция элемента меняет местами значения этого объекта и значения *right*.

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostreams](../standard-library/iostreams-conventions.md)
