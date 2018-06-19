---
title: Класс basic_ifstream | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- fstream/std::basic_ifstream
- fstream/std::basic_ifstream::close
- fstream/std::basic_ifstream::is_open
- fstream/std::basic_ifstream::open
- fstream/std::basic_ifstream::rdbuf
- fstream/std::basic_ifstream::swap
dev_langs:
- C++
helpviewer_keywords:
- std::basic_ifstream [C++]
- std::basic_ifstream [C++], close
- std::basic_ifstream [C++], is_open
- std::basic_ifstream [C++], open
- std::basic_ifstream [C++], rdbuf
- std::basic_ifstream [C++], swap
ms.assetid: 366cd9a7-efc4-4b7f-ba10-c8271e47ffcf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7b72b49f545b4ba04c92840cb4d15f2258f08680
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850617"
---
# <a name="basicifstream-class"></a>Класс basic_ifstream

Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока класса [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`> с элементами типа `Elem`, признаки символов которых определяются классом `Tr`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ifstream : public basic_istream<Elem, Tr>
```

### <a name="parameters"></a>Параметры

`Elem` Базовый элемент буфера файла.

`Tr` Признаки базового элемента буфера файла (обычно `char_traits` <  `Elem`>).

## <a name="remarks"></a>Примечания

Объект сохраняет объект класса `basic_filebuf`< `Elem`, `Tr`>.

## <a name="example"></a>Пример

В следующем примере показано, как считать текст из файла.

```cpp
// basic_ifstream_class.cpp
// compile with: /EHsc

#include <fstream>
#include <iostream>

using namespace std;

int main(int argc, char **argv)
{
    ifstream ifs("basic_ifstream_class.txt");
    if (!ifs.bad())
    {
        // Dump the contents of the file to cout.
        cout << ifs.rdbuf();
        ifs.close();
    }
}
```

## <a name="input-basicifstreamclasstxt"></a>Входные данные: basic_ifstream_class.txt

```cpp
This is the contents of basic_ifstream_class.txt.
```

## <a name="output"></a>Вывод

```cpp
This is the contents of basic_ifstream_class.txt.
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_ifstream](#basic_ifstream)|Выполняет инициализацию нового экземпляра объекта `basic_ifstream`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[close](#close)|Закрывает файл.|
|[is_open](#is_open)|Определяет, открыт ли файл.|
|[open](#open)|Открывает файл.|
|[rdbuf](#rdbuf)|Возвращает адрес сохраненного буфера потока.|
|[swap](#swap)|Меняет местами содержимое этого `basic_ifstream` и содержимое указанного параметра `basic_ifstream`.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор=](#op_eq)|Назначает содержимое этого объекта потока. Это назначение перемещения, включающее `rvalue`, которое не оставляет копию.|

## <a name="requirements"></a>Требования

**Заголовок:** \<fstream>

**Пространство имен:** std

## <a name="basic_ifstream"></a>  basic_ifstream::basic_ifstream

Создает объект типа `basic_ifstream`.

```cpp
basic_ifstream();

explicit basic_ifstream(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::in,
    int _Prot = (int)ios_base::_Openprot);

explicit basic_ifstream(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::in,
    int _Prot = (int)ios_base::_Openprot);

basic_ifstream(basic_ifstream&& right);
```

### <a name="parameters"></a>Параметры

`_Filename` Имя открываемого файла.

`_Mode` Одно из перечислений в [ios_base::openmode](../standard-library/ios-base-class.md#openmode).

`_Prot` Открытие защиты, эквивалентно файл по умолчанию `shflag` параметр в [_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md).

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует базовый класс путем вызова [basic_istream](../standard-library/basic-istream-class.md)( `sb`), где `sb` — сохраненный объект класса [basic_filebuf](../standard-library/basic-filebuf-class.md)< `Elem`, `Tr`>. Он также инициализирует `sb` путем вызова `basic_filebuf`< `Elem`, `Tr`>.

Второй и третий конструкторы инициализируют базовый класс путем вызова `basic_istream`( `sb`). Он также инициализирует `sb` путем вызова [basic_filebuf](../standard-library/basic-filebuf-class.md#basic_filebuf)< `Elem`, `Tr`>, затем `sb`. [open](../standard-library/basic-filebuf-class.md#open)( `_Filename`, `_Mode` &#124; `ios_base::in`). Если последняя функция возвращает пустой указатель, конструктор вызывает **setstate**( `failbit`).

Четвертый конструктор инициализирует объект с содержимым `right`, что рассматривается как ссылка rvalue.

### <a name="example"></a>Пример

В следующем примере показано, как считать текст из файла. Чтобы создать файл, см. пример для [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream).

```cpp
// basic_ifstream_ctor.cpp
// compile with: /EHsc

#include <fstream>
#include <iostream>

using namespace std;

int main(int argc, char **argv)
{
    ifstream ifs("basic_ifstream_ctor.txt");
    if (!ifs.bad())
    {
        // Dump the contents of the file to cout.
        cout << ifs.rdbuf();
        ifs.close();
    }
}
```

## <a name="close"></a>  basic_ifstream::close

Закрывает файл.

```cpp
void close();
```

### <a name="remarks"></a>Примечания

Функция-член вызывает [rdbuf](#rdbuf) **->** [закрыть](../standard-library/basic-filebuf-class.md#close).

### <a name="example"></a>Пример

Пример, в котором используется функция **close**, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="is_open"></a>  basic_ifstream::is_open

Определяет, открыт ли файл.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если файл открыт, или **false** в противном случае.

### <a name="remarks"></a>Примечания

Функция-член возвращает [rdbuf](#rdbuf) **->** [is_open](../standard-library/basic-filebuf-class.md#is_open).

### <a name="example"></a>Пример

Пример, в котором используется `is_open`, см. в разделе [basic_filebuf::is_open](../standard-library/basic-filebuf-class.md#is_open).

## <a name="open"></a>  basic_ifstream::open

Открывает файл.

```cpp
void open(
    const char* _Filename,
    ios_base::openmode _Mode = ios_base::in,
    int _Prot = (int)ios_base::_Openprot);

void open(
    const char* _Filename,
    ios_base::openmode _Mode);

void open(
    const wchar_t* _Filename,
    ios_base::openmode _Mode = ios_base::in,
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

Эта функция-член вызывает [rdbuf](#rdbuf) **->** [open](../standard-library/basic-filebuf-class.md#open)(_ *Filename*, `_Mode` &#124; **ios_base::in**). Если открытие завершается неудачно, функция вызывает [setstate](../standard-library/basic-ios-class.md#setstate)( **failbit**), что может создать исключение ios_base::failure.

### <a name="example"></a>Пример

Пример, в котором используется функция **open**, см. в разделе [basic_filebuf::open](../standard-library/basic-filebuf-class.md#open).

## <a name="op_eq"></a>  basic_ifstream::operator=

Назначает содержимое этого объекта потока. Это назначение перемещения, включающее rvalue, которое не оставляет копию.

```cpp
basic_ifstream& operator=(basic_ifstream&& right);
```

### <a name="parameters"></a>Параметры

`right` Ссылка rvalue на `basic_ifstream` объекта.

### <a name="return-value"></a>Возвращаемое значение

Возвращает `*this`.

### <a name="remarks"></a>Примечания

Оператор-член заменяет содержимое объекта при помощи содержимого `right`, которое обрабатывается как ссылка rvalue. Дополнительные сведения см. в разделе [Значения Lvalue и Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md).

## <a name="rdbuf"></a>  basic_ifstream::rdbuf

Возвращает адрес сохраненного буфера потока.

```cpp
basic_filebuf<Elem, Tr> *rdbuf() const
```

### <a name="return-value"></a>Возвращаемое значение

Указатель на объект [basic_filebuf](../standard-library/basic-filebuf-class.md), представляющий буфер сохраненного потока.

### <a name="example"></a>Пример

Пример, в котором используется `rdbuf`, см. в разделе [basic_filebuf::close](../standard-library/basic-filebuf-class.md#close).

## <a name="swap"></a>  basic_ifstream::swap

Меняет местами содержимое двух объектов `basic_ifstream`.

```cpp
void swap(basic_ifstream& right);
```

### <a name="parameters"></a>Параметры

`right` Ссылка на другой буфер потока.

### <a name="remarks"></a>Примечания

Функция-член меняет местами содержимое этого объекта для содержимого `right`.

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
