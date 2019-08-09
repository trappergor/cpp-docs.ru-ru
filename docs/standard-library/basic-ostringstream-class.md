---
title: Класс basic_ostringstream
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_ostringstream
- sstream/std::basic_ostringstream::allocator_type
- sstream/std::basic_ostringstream::rdbuf
- sstream/std::basic_ostringstream::str
helpviewer_keywords:
- std::basic_ostringstream [C++]
- std::basic_ostringstream [C++], allocator_type
- std::basic_ostringstream [C++], rdbuf
- std::basic_ostringstream [C++], str
ms.assetid: aea699f7-350f-432a-acca-adbae7b483fb
ms.openlocfilehash: aa25c379e47bbe22efc78d65b3f6745e98098cbd
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68453511"
---
# <a name="basicostringstream-class"></a>Класс basic_ostringstream

Описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_ostringstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>Параметры

*Идентификатор*\
Класс распределителя.

*Elem*\
Тип основного элемента строки.

*ТС*\
Признаки символа, соответствующие основному элементу строки.

## <a name="remarks"></a>Примечания

Класс описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока с элементами типа `Elem`, признаки символов которых определяются классом `Tr`, и элементы, выделенные распределителем класс `Alloc`. Этот объект сохраняет объект класса basic_stringbuf< **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_ostringstream](#basic_ostringstream)|Создает объект типа `basic_ostringstream`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Тип является синонимом для *выделения*параметра шаблона.|

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
|-|-|
|[rdbuf](#rdbuf)|Возвращает адрес буфера сохраненного потока типа `pointer` в [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>.|
|[str](#str)|Задает или получает текст в буфере строк без изменения позиции записи.|

## <a name="requirements"></a>Требования

**Заголовок:** \<sstream>

**Пространство имен:** std

## <a name="allocator_type"></a>  basic_ostringstream::allocator_type

Тип является синонимом для *выделения*параметра шаблона.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_ostringstream"></a>  basic_ostringstream::basic_ostringstream

Создает объект типа basic_ostringstream.

```cpp
explicit basic_ostringstream(ios_base::openmode _Mode = ios_base::out);

explicit basic_ostringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::out);
```

### <a name="parameters"></a>Параметры

*_Mode*\
Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*str*\
Объект типа `basic_string`.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует базовый класс путем вызова [basic_ostream](../standard-library/basic-ostream-class.md)( **SB**), где `sb` — это сохраненный объект `Alloc`класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **elem**, **tr**>. Он также инициализирует **sb** путем вызова basic_stringbuf< **Elem**, **Tr**, `Alloc`>( `_Mode` &#124; `ios_base::out`).

Второй конструктор инициализирует базовый класс путем вызова basic_ostream( **sb**). Он также инициализируется `sb` путем вызова basic_stringbuf < **elem**, **tr**, `Alloc`> (_ *str*, `_Mode` &#124; `ios_base::out`).

## <a name="rdbuf"></a>  basic_ostringstream::rdbuf

`pointer` Возвращает адрес буфера сохраненного потока типа в [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **elem**, **tr** `Alloc`>.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Возвращаемое значение

Адрес буфера `pointer` сохраненного потока типа в basic_stringbuf < **elem**, **tr** `Alloc`>.

### <a name="remarks"></a>Примечания

Функция – член `pointer` возвращает адрес буфера сохраненного потока типа в basic_stringbuf < **elem**, **tr** `Alloc`>.

### <a name="example"></a>Пример

Пример, в котором используется `rdbuf`, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="str"></a>  basic_ostringstream::str

Задает или получает текст в буфере строк без изменения позиции записи.

```cpp
basic_string<Elem, Tr, Alloc> str() const;

void str(
    const basic_string<Elem, Tr, Alloc>& _Newstr);
```

### <a name="parameters"></a>Параметры

*_Newstr*\
Новая строка.

### <a name="return-value"></a>Возвращаемое значение

Возвращает объект класса [basic_string](../standard-library/basic-string-class.md)< **Elem**, **Tr**, `Alloc`>, управляемая последовательность которого является копией последовательности, управляемой **\*this**.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает [rdbuf](#rdbuf) -> [str](../standard-library/basic-stringbuf-class.md#str). Вторая функция-член вызывает `rdbuf` -> **str**( `_Newstr`).

### <a name="example"></a>Пример

Пример, в котором используется `str`, см. в разделе [basic_stringbuf:: str](../standard-library/basic-stringbuf-class.md#str) .

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostreams](../standard-library/iostreams-conventions.md)
