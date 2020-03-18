---
title: Класс basic_ofstream
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_ofstream
- fstream/std::basic_ofstream::close
- fstream/std::basic_ofstream::is_open
- fstream/std::basic_ofstream::open
- fstream/std::basic_ofstream::rdbuf
- fstream/std::basic_ofstream::swap
helpviewer_keywords:
- std::basic_ofstream [C++]
- std::basic_ofstream [C++], close
- std::basic_ofstream [C++], is_open
- std::basic_ofstream [C++], open
- std::basic_ofstream [C++], rdbuf
- std::basic_ofstream [C++], swap
ms.assetid: 3bcc9c51-6dfc-4844-8fcc-22ef57c9dff1
ms.openlocfilehash: a73803f25c4fb9e54703b8bca93e68fedb63074e
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424065"
---
# <a name="basic_ofstream-class"></a>Класс basic_ofstream

Описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> с элементами типа `Elem`, признаки символов которых определяются классом `Tr`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ofstream : public basic_ostream<Elem, Tr>
```

### <a name="parameters"></a>Параметры

*Elem*\
Базовый элемент буфера файла.

*Tr*\
Признаки базового элемента буфера файла (обычно `char_traits`< `Elem`>).

## <a name="remarks"></a>Remarks

При **wchar_t** специализации `basic_ofstream` записи в файл, если файл открыт в текстовом режиме, будет записана последовательность MBCS. Внутреннее представление будет использовать буфер символов `wchar_t`.

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

|Конструктор|Description|
|-|-|
|[basic_ofstream](#basic_ofstream)|Создает объект типа `basic_ofstream`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Description|
|-|-|
|[close](#close)|Закрывает файл.|
|[is_open](#is_open)|Определяет, открыт ли файл.|
|[open](#open)|Открывает файл.|
|[rdbuf](#rdbuf)|Возвращает адрес сохраненного буфера потока.|
|[swap](#swap)|Меняет местами содержимое этого объекта `basic_ofstream` с содержимым указанного объекта `basic_ofstream`.|

### <a name="operators"></a>Операторы

|Оператор|Description|
|-|-|
|[оператор=](#op_eq)|Назначает содержимое этого объекта потока. Это назначение перемещения, включающее `rvalue reference`, которое не оставляет копию.|

## <a name="requirements"></a>Требования

**Заголовок:** \<FStream >

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

*_Filename*\
Имя файла, который необходимо открыть.

*_Mode*\
Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*\
Защита открытия файла по умолчанию, эквивалент параметра `shflag` в [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

*справа*\
Ссылка rvalue на объект `basic_ofstream`, используемый для инициализации этого объекта `basic_ofstream`.

### <a name="remarks"></a>Remarks

Первый конструктор инициализирует базовый класс путем вызова [basic_ostream](../standard-library/basic-ostream-class.md)(`sb`), где `sb` — это сохраненный объект класса [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>. Он также инициализирует `sb` путем вызова `basic_filebuf`< `Elem`, `Tr`>.

Второй и третий конструкторы инициализируют базовый класс путем вызова `basic_ostream`( **sb**). Он также инициализирует `sb`, вызывая `basic_filebuf`< `Elem`, `Tr`> а затем `sb`. [open](../standard-library/basic-filebuf-class.md#open)( `_Filename`, `_Mode` &#124; `ios_base::out`). Если последняя функция возвращает пустой указатель, конструктор вызывает [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`).

Четвертый конструктор является функцией копирования. Он инициализирует объект с содержимым *right*, который рассматривается как ссылка rvalue.

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

### <a name="remarks"></a>Remarks

Эта функция-член вызывает [rdbuf](../standard-library/basic-ifstream-class.md#rdbuf) **->** [close](../standard-library/basic-filebuf-class.md#close).

### <a name="example"></a>Пример

Пример, в котором используется [, см. в разделе ](../standard-library/basic-filebuf-class.md#close)basic_filebuf::close`close`.

## <a name="is_open"></a>  basic_ofstream::is_open

Указывает, открыт ли файл.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если файл открыт, или **false** в противном случае.

### <a name="remarks"></a>Remarks

Функция – член возвращает [rdbuf](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open).

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

*_Filename*\
Имя файла, который необходимо открыть.

*_Mode*\
Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*\
Защита открытия файла по умолчанию, эквивалент параметра `shflag` в [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="remarks"></a>Remarks

Функция-член вызывает [rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ *filename*, `_Mode` &#124; `ios_base::out`). Если эта функция возвращает пустой указатель, функция вызывает [SetState](../standard-library/basic-ios-class.md#setstate)(`failbit`).

### <a name="example"></a>Пример

Пример использования `open`см. в разделе [basic_filebuf:: Open](../standard-library/basic-filebuf-class.md#open) .

## <a name="op_eq"></a>  basic_ofstream::operator=

Назначает содержимое этого объекта потока. Это назначение перемещения, включающее `rvalue reference`, которое не оставляет копию.

```cpp
basic_ofstream& operator=(basic_ofstream&& right);
```

### <a name="parameters"></a>Параметры

*справа*\
Ссылка rvalue на объект `basic_ofstream`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `*this`.

### <a name="remarks"></a>Remarks

Оператор Member заменяет содержимое объекта с помощью содержимого *right*, которое рассматривается как ссылка rvalue.

## <a name="rdbuf"></a>  basic_ofstream::rdbuf

Возвращает адрес сохраненного буфера потока.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес сохраненного буфера потока.

### <a name="example"></a>Пример

Пример, в котором используется [, см. в разделе ](../standard-library/basic-filebuf-class.md#close)basic_filebuf::close`rdbuf`.

## <a name="swap"></a>  basic_ofstream::swap

Меняет местами содержимое двух объектов `basic_ofstream`.

```cpp
void swap(basic_ofstream& right);
```

### <a name="parameters"></a>Параметры

*справа*\
Ссылка `lvalue` на другой объект `basic_ofstream`.

### <a name="remarks"></a>Remarks

Функция элемента меняет местами содержимое этого объекта на содержимое, находящееся *справа*.

## <a name="see-also"></a>См. также раздел

[Класс basic_ostream](../standard-library/basic-ostream-class.md)\
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[Программирование iostream](../standard-library/iostream-programming.md)\
[Соглашения iostreams](../standard-library/iostreams-conventions.md)
