---
title: Класс basic_ofstream | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- fstream/std::basic_ofstream
- fstream/std::basic_ofstream::close
- fstream/std::basic_ofstream::is_open
- fstream/std::basic_ofstream::open
- fstream/std::basic_ofstream::rdbuf
- fstream/std::basic_ofstream::swap
dev_langs:
- C++
helpviewer_keywords:
- std::basic_ofstream [C++]
- std::basic_ofstream [C++], close
- std::basic_ofstream [C++], is_open
- std::basic_ofstream [C++], open
- std::basic_ofstream [C++], rdbuf
- std::basic_ofstream [C++], swap
ms.assetid: 3bcc9c51-6dfc-4844-8fcc-22ef57c9dff1
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f523d8471b2cdb1736e57dbc8b0d101574c42abc
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="basicofstream-class"></a>Класс basic_ofstream

Описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> с элементами типа `Elem`, признаки символов которых определяются классом `Tr`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ofstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>Параметры

`Elem` Базовый элемент буфера файла.

`Tr` Признаки базового элемента буфера файла (обычно `char_traits` <  `Elem`>).

## <a name="remarks"></a>Примечания

Если файл открыт в текстовом режиме, то при записи специализации `wchar_t` `basic_ofstream` в файл будет записана последовательность MBCS. Внутреннее представление будет использовать буфер символов `wchar_t`.

Объект сохраняет объект класса `basic_filebuf`< `Elem`, `Tr`>.

## <a name="example"></a>Пример

В следующем примере показано создание объекта `basic_ofstream` и запись в него текста.

```cpp
// basic_ofstream_class.cpp
// compile with: /EHsc
#include <fstream>

using namespace std;

int main(int argc, char **argv)
{
    ofstream ofs("ofstream.txt");
    if (!ofs.bad())
    {
        ofs << "Writing to a basic_ofstream object..." << endl;
        ofs.close();
    }
}
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_ofstream](#basic_ofstream)|Создает объект типа `basic_ofstream`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[close](#close)|Закрывает файл.|
|[is_open](#is_open)|Определяет, открыт ли файл.|
|[open](#open)|Открывает файл.|
|[rdbuf](#rdbuf)|Возвращает адрес сохраненного буфера потока.|
|[swap](#swap)|Меняет местами содержимое этого объекта `basic_ofstream` с содержимым указанного объекта `basic_ofstream`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор=](#op_eq)|Назначает содержимое этого объекта потока. Это назначение перемещения, включающее `rvalue reference`, которое не оставляет копию.|

## <a name="requirements"></a>Требования

**Заголовок:** \<fstream>

**Пространство имен:** std

## <a name="basic_ofstream"></a>  basic_ofstream::basic_ofstream

Создает объект типа `basic_ofstream`.

```cpp
basic_ofstream();

explicit basic_ofstream(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

explicit basic_ofstream(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

basic_ofstream(
    basic_ofstream&& right);
```

### <a name="parameters"></a>Параметры

`_Filename` Имя открываемого файла.

`_Mode` Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

`_Prot` Открытие защиты, эквивалентно файл по умолчанию `shflag` параметр в [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

`right` Ссылка rvalue на `basic_ofstream` , применяемый для инициализации этого `basic_ofstream` объекта.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует базовый класс путем вызова [basic_iostream](../standard-library/basic-ostream-class.md)( **sb**), где **sb** — сохраненный объект класса [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>. Он также инициализирует **sb** путем вызова `basic_filebuf`< `Elem`, `Tr`>.

Второй и третий конструкторы инициализируют базовый класс путем вызова `basic_ostream`( **sb**). Они также инициализируют **sb** путем вызова `basic_filebuf`< `Elem`, `Tr`>, а затем **sb**. [open](../standard-library/basic-filebuf-class.md#open)( `_Filename`, `_Mode` &#124; `ios_base::out`). Если последняя функция возвращает пустой указатель, конструктор вызывает [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**).

Четвертый конструктор является функцией копирования. Он инициализирует объект с содержимым `right`, что рассматривается как ссылка rvalue.

### <a name="example"></a>Пример

В следующем примере показано создание объекта `basic_ofstream` и запись в него текста.

```cpp
// basic_ofstream_ctor.cpp
// compile with: /EHsc
#include <fstream>

using namespace std;

int main(int argc, char **argv)
{
    ofstream ofs("C:\\ofstream.txt");
    if (!ofs.bad())
    {
        ofs << "Writing to a basic_ofstream object..." << endl;
        ofs.close();
    }
}
```

## <a name="close"></a>  basic_ofstream::close

Закрывает файл.

```cpp
void close();
```

### <a name="remarks"></a>Примечания

Функция-член вызывает [rdbuf](../standard-library/basic-ifstream-class.md#rdbuf)**->**[закрыть](../standard-library/basic-filebuf-class.md#close).

### <a name="example"></a>Пример

Пример, в котором используется функция **close**, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="is_open"></a>  basic_ofstream::is_open

Указывает, открыт ли файл.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение `true`, если файл открыт; в противном случае — значение `false`.

### <a name="remarks"></a>Примечания

Функция-член возвращает [rdbuf](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open).

### <a name="example"></a>Пример

```cpp
// basic_ofstream_is_open.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main( )
{
   using namespace std;
   ifstream file;
   // Open and close with a basic_filebuf
   file.rdbuf( )->open( "basic_ofstream_is_open.txt", ios::in );
   file.close( );
   if (file.is_open())
      cout << "it's open" << endl;
   else
      cout << "it's closed" << endl;
}
```

## <a name="open"></a>  basic_ofstream::open

Открывает файл.

```cpp
void open(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::out,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode);
```

### <a name="parameters"></a>Параметры

`_Filename` Имя открываемого файла.

`_Mode` Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

`_Prot` Открытие защиты, эквивалентно файл по умолчанию `shflag` параметр в [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="remarks"></a>Примечания

Эта функция-член вызывает [rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode` &#124; `ios_base::out`). Если эта функция возвращает пустой указатель, конструктор вызывает [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**).

### <a name="example"></a>Пример

Пример, в котором используется функция **open**, см. в разделе [basic_filebuf::open](../standard-library/basic-filebuf-class.md#open).

## <a name="op_eq"></a>  basic_ofstream::operator=

Назначает содержимое этого объекта потока. Это назначение перемещения, включающее `rvalue reference`, которое не оставляет копию.

```cpp
basic_ofstream& operator=(basic_ofstream&& right);
```

### <a name="parameters"></a>Параметры

`right` Ссылка rvalue на `basic_ofstream` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `*this`.

### <a name="remarks"></a>Примечания

Оператор-член заменяет содержимое объекта при помощи содержимого `right`, которое обрабатывается как ссылка rvalue.

## <a name="rdbuf"></a>  basic_ofstream::rdbuf

Возвращает адрес сохраненного буфера потока.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес сохраненного буфера потока.

### <a name="example"></a>Пример

Пример, в котором используется `rdbuf`, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="swap"></a>  basic_ofstream::swap

Меняет местами содержимое двух объектов `basic_ofstream`.

```cpp
void swap(basic_ofstream& right);
```

### <a name="parameters"></a>Параметры

`right` `lvalue` Ссылаться на другой `basic_ofstream` объекта.

### <a name="remarks"></a>Примечания

Функция-член меняет местами содержимое этого объекта для содержимого `right`.

## <a name="see-also"></a>См. также

[Класс basic_ostream](../standard-library/basic-ostream-class.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
