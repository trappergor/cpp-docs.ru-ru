---
title: Класс basic_ostream
ms.date: 11/04/2016
f1_keywords:
- ostream/std::basic_ostream
- ostream/std::basic_ostream::flush
- ostream/std::basic_ostream::put
- ostream/std::basic_ostream::seekp
- ostream/std::basic_ostream::sentry
- ostream/std::basic_ostream::swap
- ostream/std::basic_ostream::tellp
- ostream/std::basic_ostream::write
helpviewer_keywords:
- std::basic_ostream [C++]
- std::basic_ostream [C++], flush
- std::basic_ostream [C++], put
- std::basic_ostream [C++], seekp
- std::basic_ostream [C++], sentry
- std::basic_ostream [C++], swap
- std::basic_ostream [C++], tellp
- std::basic_ostream [C++], write
ms.assetid: 5baadc65-b662-4fab-8c9f-94457c58cda1
ms.openlocfilehash: dce4911bd4b7abe6c73551d6a0b178d9b2700dbb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543641"
---
# <a name="basicostream-class"></a>Класс basic_ostream

Этот класс шаблона описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока с элементами типа `Elem`, также известных как [char_type](../standard-library/basic-ios-class.md#char_type), признаки символов определяются классом `Tr`, также известных как [traits_type](../standard-library/basic-ios-class.md#traits_type).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ostream : virtual public basic_ios<Elem, Tr>
```

### <a name="parameters"></a>Параметры

*Elem*<br/>
Объект `char_type`.

*Tr*<br/>
`traits_type` символа.

## <a name="remarks"></a>Примечания

Большинство функций-членов, которые перегружают [operator<<](#op_lt_lt),  — это форматированные выходные функции. Они следуют этому шаблону:

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (ok)
{try
{<convert and insert elements
    accumulate flags in state> }
    catch (...)
{try
{setstate(badbit);

}
    catch (...)
{}
    if ((exceptions()& badbit) != 0)
    throw; }}
width(0);
// Except for operator<<(Elem)
setstate(state);

return (*this);
```

Две другие функции-члены — это неформатированные выходные функции. Они следуют этому шаблону:

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (!ok)
    state |= badbit;
else
{try
{<obtain and insert elements
    accumulate flags in state> }
    catch (...)
{try
{setstate(badbit);

}
    catch (...)
{}
    if ((exceptions()& badbit) != 0)
    throw; }}
setstate(state);

return (*this);
```

Обе группы функций вызывают [setstate](../standard-library/basic-ios-class.md#setstate)(**badbit**) при обнаружении ошибки вставки элементов.

Объект класса basic_istream\< **Elem**, **Tr**> хранит только виртуальный открытый базовый объект класса [basic_ios](../standard-library/basic-ios-class.md)**\<Elem**, **Tr>**.

## <a name="example"></a>Пример

Дополнительные сведения о выходных потоках см. в примере для [класса basic_ofstream](../standard-library/basic-ofstream-class.md).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_ostream](#basic_ostream)|Создает объект `basic_ostream`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[flush](#flush)|Очищает буфер.|
|[put](#put)|Помещает символ в поток.|
|[seekp](#seekp)|Сбрасывает позицию в потоке вывода.|
|[sentry](#sentry)|Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные выходные функции.|
|[swap](#op_eq)|Меняет местами значения в этом объекте `basic_ostream` и значения предоставленного объекта `basic_ostream`.|
|[tellp](#tellp)|Сообщает позицию в потоке вывода.|
|[write](#write)|Помещает символы в поток.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор=](#basic_ostream_operator_eq)|Присваивает значение указанного параметра объекта `basic_ostream` этому объекту.|
|[оператор<<](#basic_ostream_operator_lt_lt)|Записывает данные в поток.|

## <a name="requirements"></a>Требования

**Заголовок:** \<ostream>

**Пространство имен:** std

## <a name="basic_ostream"></a>  basic_ostream::basic_ostream

Создает объект `basic_ostream`.

```cpp
explicit basic_ostream(
    basic_streambuf<Elem, Tr>* strbuf,
    bool _Isstd = false);

basic_ostream(basic_ostream&& right);
```

### <a name="parameters"></a>Параметры

*strbuf*<br/>
Объект типа [basic_streambuf](../standard-library/basic-streambuf-class.md).

*_Isstd*<br/>
**значение true,** Если это стандартный поток; в противном случае **false**.

*right*<br/>
Ссылка rvalue на объект типа `basic_ostream`.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует базовый класс путем вызова [init](../standard-library/basic-ios-class.md#init)(`strbuf`). Второй конструктор инициализирует базовый класс путем вызова [basic_ios::move](../standard-library/basic-ios-class.md#move)`(right)`.

### <a name="example"></a>Пример

Дополнительные сведения о выходных потоках см. в примере для [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream).

## <a name="flush"></a>  basic_ostream::flush

Очищает буфер.

```cpp
basic_ostream<Elem, Tr>& flush();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект basic_ostream.

### <a name="remarks"></a>Примечания

Если [rdbuf](../standard-library/basic-ios-class.md#rdbuf) не является пустым указателем, функция вызывает **rdbuf->**[pubsync](../standard-library/basic-streambuf-class.md#pubsync). Если возвращается значение –1, функция вызывает [setstate](../standard-library/basic-ios-class.md#setstate)(**badbit**). Она возвращает **\*this**.

### <a name="example"></a>Пример

```cpp
// basic_ostream_flush.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout << "test";
   cout.flush();
}
```

```Output
test
```

## <a name="basic_ostream_operator_lt_lt"></a> basic_ostream::operator&lt;&lt;

Записывает данные в поток.

```cpp
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& (* Pfn)(basic_ostream<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(
    ios_base& (* Pfn)(ios_base&));

basic_ostream<Elem, Tr>& operator<<(
    basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
basic_ostream<Elem, Tr>& operator<<(bool val);
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int __w64  val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long __w64  val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```

### <a name="parameters"></a>Параметры

*pfn-имени*<br/>
Указатель функции.

*strbuf*<br/>
Указатель на объект `stream_buf` .

*Val*<br/>
Элемент, записываемый в поток.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект basic_ostream.

### <a name="remarks"></a>Примечания

\<Ostream > заголовок также определяет несколько глобальных операторов вставки. Дополнительные сведения см. в разделе [оператор <<](../standard-library/ostream-operators.md#op_lt_lt).

Первая функция-член обеспечивает, чтобы выражение в форме `ostr << endl` вызовы [endl](../standard-library/ostream-functions.md#endl)**(ostr)**, а затем возвращает  **\*это**. Вторая и третья функции обеспечивают аналогичное поведение других манипуляторов, таких как [hex](../standard-library/ios-functions.md#hex). Все остальные функции являются форматированными выходными функциями.

Функция

```cpp
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```

Извлекает элементы из *strbuf*, если *strbuf* не является указателем null и вставляет их. Извлечение останавливается в конце файла или если оно создает исключение (которое создается повторно). Оно также останавливается без извлечения соответствующего элемента, если вставка завершается неудачно. Если функция не вставляет элементы или если вставка создает исключение, эта функция вызывает [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). В любом случае эта функция возвращает **\*this**.

Функция

```cpp
basic_ostream<Elem, Tr>& operator<<(bool val);
```

Преобразует `_Val` в логическое поле и вставляет его путем вызова [use_facet](../standard-library/basic-filebuf-class.md#open)**< num_put\<Elem, OutIt >**`(`[getloc](../standard-library/ios-base-class.md#getloc)). [put](#put)(**OutIt**([rdbuf](../standard-library/basic-ios-class.md#rdbuf)), **\*this**, `getloc`, **val**). Здесь `OutIt` определяется как [ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md)**\<Elem, Tr >**. Функция возвращает **\*this**.

Каждая из функций

```cpp
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```

Преобразует *val* в числовое поле и вставляет его путем вызова **use_facet < num_put\<Elem, OutIt >**(`getloc`). **put**(**OutIt**(`rdbuf`), **\*this**, `getloc`, **val**). Здесь **OutIt** определяется как **ostreambuf_iterator\<Elem, Tr>**. Функция возвращает **\*this**.

Каждая из функций

```cpp
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```

Преобразует *val* в числовое поле и вставляет его путем вызова **use_facet < num_put\<Elem, OutIt >**(`getloc`)**. Поместите**(**OutIt**(`rdbuf`),  **\*это**, `getloc`, **val**). Здесь **OutIt** определяется как **ostreambuf_iterator\<Elem, Tr>**. Функция возвращает **\*this**.

### <a name="example"></a>Пример

```cpp
// basic_ostream_op_write.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;

ios_base& hex2( ios_base& ib )
{
   ib.unsetf( ios_base::dec );
   ib.setf( ios_base::hex );
   return ib;
}

basic_ostream<char, char_traits<char> >& somefunc(basic_ostream<char, char_traits<char> > &i)
{
    if (i == cout)
    {
        i << "i is cout" << endl;
    }
    return i;
}

class CTxtStreambuf : public basic_streambuf< char, char_traits< char > >
{
public:
    CTxtStreambuf(char *_pszText)
    {
        pszText = _pszText;
        setg(pszText, pszText, pszText + strlen(pszText));
    };
    char *pszText;
};

int main()
{
    cout << somefunc;
    cout << 21 << endl;

    hex2(cout);
    cout << 21 << endl;

    CTxtStreambuf f("text in streambuf");
    cout << &f << endl;
}
```

## <a name="op_eq"></a>  basic_ostream::operator=

Присваивает значения указанного параметра объекта `basic_ostream` этому объекту.

```cpp
basic_ostream& operator=(basic_ostream&& right);
```

### <a name="parameters"></a>Параметры

*right*<br/>
Ссылка `rvalue` на объект `basic_ostream`.

### <a name="remarks"></a>Примечания

Оператор-член вызывает swap `(right)`.

## <a name="put"></a>  basic_ostream::put

Помещает символ в поток.

```cpp
basic_ostream<Elem, Tr>& put(char_type _Ch);
```

### <a name="parameters"></a>Параметры

*_Ch*<br/>
Символ.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект basic_ostream.

### <a name="remarks"></a>Примечания

Неформатированная выходная функция вставляет элемент *_Ch*. Она возвращает **\*this**.

### <a name="example"></a>Пример

```cpp
// basic_ostream_put.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   cout.put( 'v' );
   cout << endl;
   wcout.put( L'l' );
}
```

```Output
v
l
```

## <a name="seekp"></a>  basic_ostream::seekp

Сбрасывает позицию в выходном потоке.

```cpp
basic_ostream<Elem, Tr>& seekp(pos_type _Pos);

basic_ostream<Elem, Tr>& seekp(off_type _Off, ios_base::seekdir _Way);
```

### <a name="parameters"></a>Параметры

*_Pos*<br/>
Позиция в потоке.

*_Off*<br/>
Смещение относительно *_Way*.

*_Way*<br/>
Одно из перечислений [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir).

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект basic_ostream.

### <a name="remarks"></a>Примечания

Если [ошибкой](../standard-library/basic-ios-class.md#fail) — **false**, первая функция-член вызывает **newpos =** [rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)(*_Pos*), для некоторых `pos_type` временный объект `newpos`. Если `fail` имеет значение false, вторая функция вызывает **newpos = rdbuf - >** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(*_Off, _Way*). В любом случае, если (`off_type`)**newpos ==** (`off_type`)(–1) (операция размещения завершается неудачно), функция вызывает **istr.**[setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). Обе функции возвращают **\*this**.

### <a name="example"></a>Пример

```cpp
// basic_ostream_seekp.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main()
{
    using namespace std;
    ofstream x("basic_ostream_seekp.txt");
    streamoff i = x.tellp();
    cout << i << endl;
    x << "testing";
    i = x.tellp();
    cout << i << endl;
    x.seekp(2);   // Put char in third char position in file
    x << " ";

    x.seekp(2, ios::end);   // Put char two after end of file
    x << "z";
}
```

```Output
0
7
```

## <a name="sentry"></a>  basic_ostream::sentry

Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные выходные функции.

Класс sentry {открытый: явные sentry (basic_ostream\<Elem, Tr > & _Ostr); operator bool() const; ~ sentry();};

### <a name="remarks"></a>Примечания

Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные выходные функции. Если **ostr.**[good](../standard-library/basic-ios-class.md#good) имеет значение **true**, и **ostr.**[tie](../standard-library/basic-ios-class.md#tie) не является пустым указателем, конструктор вызывает **ostr.tie->**[flush](#flush). Затем конструктор сохраняет значение, возвращенное `ostr.good` в `status`. Последующий вызов `operator bool` предоставляет это сохраненное значение.

Если `uncaught_exception` возвращает **false** и [flags](../standard-library/ios-base-class.md#flags) **&** [unitbuf](../standard-library/ios-functions.md#unitbuf) не равно нулю, деструктор вызывает [flush](#flush).

## <a name="swap"></a>  basic_ostream::swap

Меняет местами значения в этом объекте `basic_ostream` и значения предоставленного объекта `basic_ostream`.

```cpp
void swap(basic_ostream& right);
```

### <a name="parameters"></a>Параметры

*right*<br/>
Ссылка на объект `basic_ostream`.

### <a name="remarks"></a>Примечания

Функция-член вызывает [basic_ios::swap](../standard-library/basic-ios-class.md#swap) `(right)` для обмена содержимое этого объекта для содержимого *правой*.

## <a name="tellp"></a>  basic_ostream::tellp

Сообщает позицию в выходном потоке.

```cpp
pos_type tellp();
```

### <a name="return-value"></a>Возвращаемое значение

Позиция в выходном потоке.

### <a name="remarks"></a>Примечания

Если [fail](../standard-library/basic-ios-class.md#fail) имеет значение **false**, то функция-член возвращает [rdbuf](../standard-library/basic-ios-class.md#rdbuf)**->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(0, `cur`, **in**). В противном случае она возвращает `pos_type`(–1).

### <a name="example"></a>Пример

Пример использования `tellp` см. в разделе [seekp](#seekp).

## <a name="write"></a>  basic_ostream::write

Помещает символы в поток.

```cpp
basic_ostream<Elem, Tr>& write(const char_type* str, streamsize count);
```

### <a name="parameters"></a>Параметры

*count*<br/>
Количество символов для помещения в поток.

*str*<br/>
Символы для помещения в поток.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект basic_ostream.

### <a name="remarks"></a>Примечания

[Неформатированная выходная функция](../standard-library/basic-ostream-class.md) вставляет последовательность *число* элементы, начиная с *str*.

### <a name="example"></a>Пример

Пример использования `write` см. в разделе [streamsize](../standard-library/ios-typedefs.md#streamsize).

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
