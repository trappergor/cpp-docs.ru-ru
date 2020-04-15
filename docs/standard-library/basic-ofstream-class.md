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
ms.openlocfilehash: f2d0facd92e0ef1935f8218a6d323a62edb81e5b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376784"
---
# <a name="basic_ofstream-class"></a>Класс basic_ofstream

Описывает объект, который управляет вставкой элементов и закодированных `Tr` объектов в буфер `Elem`потока [класса basic_filebuf,](../standard-library/basic-filebuf-class.md)< `Elem`>, `Tr`с элементами типа, черты характера которых определяются классом.

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

Когда **wchar_t** специализацию записей `basic_ofstream` в файл, если файл открыт в текстовом режиме, он напишет последовательность MBCS. Внутреннее представление будет использовать буфер символов `wchar_t`.

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

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Закрыть](#close)|Закрывает файл.|
|[is_open](#is_open)|Определяет, открыт ли файл.|
|[open](#open)|Открывает файл.|
|[rdbuf](#rdbuf)|Возвращает адрес сохраненного буфера потока.|
|[Своп](#swap)|Меняет местами содержимое этого объекта `basic_ofstream` с содержимым указанного объекта `basic_ofstream`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператора](#op_eq)|Назначает содержимое этого объекта потока. Это назначение перемещения, включающее `rvalue reference`, которое не оставляет копию.|

## <a name="requirements"></a>Требования

**Заголовок:** \<fstream>

**Пространство имен:** std

## <a name="basic_ofstreambasic_ofstream"></a><a name="basic_ofstream"></a>basic_ofstream::basic_ofstream

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

*_mode*\
Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*\
Защита открытия файла по умолчанию, эквивалент параметра `shflag` в [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

*Правильно*\
Ссылка rvalue на объект `basic_ofstream`, используемый для инициализации этого объекта `basic_ofstream`.

### <a name="remarks"></a>Remarks

Первый конструктор инициализирует базовый`sb`класс, `sb` позвонив [basic_ostream](../standard-library/basic-ostream-class.md) `Tr` (), где находится хранимый объект класса [basic_filebuf,](../standard-library/basic-filebuf-class.md)< `Elem`>. Он также инициализирует `sb` путем вызова `basic_filebuf`< `Elem`, `Tr`>.

Второй и третий конструкторы инициализируют базовый класс путем вызова `basic_ostream`( **sb**). Он `sb` также инициализирует, позвонив, `basic_filebuf` <  `Elem` `Tr`>, а затем `sb`. [открыть](../standard-library/basic-filebuf-class.md#open) `_Filename` `_Mode` (, `ios_base::out`&#124; ). Если последняя функция возвращает нулевую указку,`failbit`конструктор вызывает [setstate](../standard-library/basic-ios-class.md#setstate)( ).

Четвертый конструктор является функцией копирования. Он инициирует объект с содержимым *права,* рассматривается как ссылка rvalue.

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

## <a name="basic_ofstreamclose"></a><a name="close"></a>basic_ofstream::закрыть

Закрывает файл.

```cpp
void close();
```

### <a name="remarks"></a>Remarks

Функция члена вызывает [rdbuf](../standard-library/basic-ifstream-class.md#rdbuf)**->**[близко.](../standard-library/basic-filebuf-class.md#close)

### <a name="example"></a>Пример

Пример, в котором используется `close`, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="basic_ofstreamis_open"></a><a name="is_open"></a>basic_ofstream::is_open

Указывает, открыт ли файл.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если файл открыт, или **false** в противном случае.

### <a name="remarks"></a>Remarks

Функция члена возвращает [rdbuf](#rdbuf) **->** [is_open.](../standard-library/basic-filebuf-class.md#is_open)

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

## <a name="basic_ofstreamopen"></a><a name="open"></a>basic_ofstream::открыто

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

*_mode*\
Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

*_Prot*\
Защита открытия файла по умолчанию, эквивалент параметра `shflag` в [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="remarks"></a>Remarks

Функция члена вызывает [rdbuf](#rdbuf) **->** [открыто](../standard-library/basic-filebuf-class.md#open)(я `ios_base::out` *Filename,* `_Mode` &#124;). Если эта функция возвращает нулевую указку, функция вызывает [setstate](../standard-library/basic-ios-class.md#setstate)(`failbit`).

### <a name="example"></a>Пример

Смотрите [basic_filebuf::открыть](../standard-library/basic-filebuf-class.md#open) для примера, который использует `open`.

## <a name="basic_ofstreamoperator"></a><a name="op_eq"></a>basic_ofstream:оператор

Назначает содержимое этого объекта потока. Это назначение перемещения, включающее `rvalue reference`, которое не оставляет копию.

```cpp
basic_ofstream& operator=(basic_ofstream&& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Ссылка rvalue на объект `basic_ofstream`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `*this`.

### <a name="remarks"></a>Remarks

Оператор-член заменяет содержимое объекта, используя содержимое *права,* отнесемый к ссылке rvalue.

## <a name="basic_ofstreamrdbuf"></a><a name="rdbuf"></a>basic_ofstream::rdbuf

Возвращает адрес сохраненного буфера потока.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает адрес сохраненного буфера потока.

### <a name="example"></a>Пример

Пример, в котором используется `rdbuf`, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="basic_ofstreamswap"></a><a name="swap"></a>basic_ofstream::swap

Меняет местами содержимое двух объектов `basic_ofstream`.

```cpp
void swap(basic_ofstream& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Ссылка `lvalue` на другой объект `basic_ofstream`.

### <a name="remarks"></a>Remarks

Функция участника обменивается содержимое этого объекта на содержимое *права.*

## <a name="see-also"></a>См. также раздел

[класс basic_ostream](../standard-library/basic-ostream-class.md)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[программирование йострима](../standard-library/iostream-programming.md)\
[iostreams Конвенций](../standard-library/iostreams-conventions.md)
