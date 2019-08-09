---
title: Класс basic_stringstream
ms.date: 11/04/2016
f1_keywords:
- sstream/std::basic_stringstream
- sstream/std::basic_stringstream::allocator_type
- sstream/std::basic_stringstream::rdbuf
- sstream/std::basic_stringstream::str
helpviewer_keywords:
- std::basic_stringstream [C++]
- std::basic_stringstream [C++], allocator_type
- std::basic_stringstream [C++], rdbuf
- std::basic_stringstream [C++], str
ms.assetid: 49629814-ca37-45c5-931b-4ff894e6ebd2
ms.openlocfilehash: 9278b6ce0fa23fa875f1af57ea15719111439372
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447807"
---
# <a name="basicstringstream-class"></a>Класс basic_stringstream

Описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class Tr = char_traits<Elem>, class Alloc = allocator<Elem>>
class basic_stringstream : public basic_iostream<Elem, Tr>
```

### <a name="parameters"></a>Параметры

*Идентификатор*\
Класс распределителя.

*Elem*\
Тип основного элемента строки.

*ТС*\
Признаки символа, соответствующие основному элементу строки.

## <a name="remarks"></a>Примечания

Класс шаблона описывает объект, управляющий вставкой и извлечением элементов и закодированных объектов с помощью буфера потока класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **elem**, **tr** `Alloc`> с элементами типа .`Elem`, признаки символов которых определяются классом `Tr`, элементы которого выделяются распределителем класса `Alloc`. Этот объект сохраняет объект класса basic_stringbuf< **Elem**, **Tr**, `Alloc`>.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_stringstream](#basic_stringstream)|Создает объект типа `basic_stringstream`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[allocator_type](#allocator_type)|Этот тип является синонимом для параметра шаблона `Alloc`.|

### <a name="member-functions"></a>Функции-члены

|Функция Member|Описание|
|-|-|
|[rdbuf](#rdbuf)|Возвращает адрес буфера сохраненного потока типа `pointer` в [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< `Elem`, `Tr`, `Alloc`>.|
|[str](#str)|Задает или получает текст в буфере строк без изменения позиции записи.|

## <a name="requirements"></a>Требования

**Заголовок:** \<sstream>

**Пространство имен:** std

## <a name="allocator_type"></a>  basic_stringstream::allocator_type

Этот тип является синонимом для параметра шаблона `Alloc`.

```cpp
typedef Alloc allocator_type;
```

## <a name="basic_stringstream"></a>  basic_stringstream::basic_stringstream

Создает объект типа `basic_stringstream`.

```cpp
explicit basic_stringstream(ios_base::openmode _Mode = ios_base::in | ios_base::out);

explicit basic_stringstream(const basic_string<Elem, Tr, Alloc>& str, ios_base::openmode _Mode = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

*_Mode*\
Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*str*\
Объект типа `basic_string`.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует базовый класс путем вызова [basic_iostream](../standard-library/basic-iostream-class.md)( **SB**), где `sb` — это сохраненный объект `Alloc`класса [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **elem**, **tr**>. Он также инициализируется `sb` путем вызова basic_stringbuf < **elem**, **tr**, `Alloc`> ( `_Mode`).

Второй конструктор инициализирует базовый класс путем вызова basic_iostream( **sb**). Он также инициализируется `sb` путем вызова basic_stringbuf < **elem**, **tr**, `Alloc`> (_ *str*, `_Mode`).

## <a name="rdbuf"></a>  basic_stringstream::rdbuf

Возвращает адрес буфера сохраненного потока типа **pointer** в [basic_stringbuf](../standard-library/basic-stringbuf-class.md)< **Elem**, **Tr**, `Alloc`>.

```cpp
basic_stringbuf<Elem, Tr, Alloc> *rdbuf() const;
```

### <a name="return-value"></a>Возвращаемое значение

Адрес буфера `pointer` сохраненного потока типа в basic_stringbuf < **elem**, **tr** `Alloc`>.

### <a name="example"></a>Пример

Пример, в котором используется `rdbuf`, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="str"></a>  basic_stringstream::str

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
