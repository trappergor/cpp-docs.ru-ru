---
title: Класс basic_ostream
ms.date: 03/27/2019
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
ms.openlocfilehash: e074eb30d31c316411dd43f9a7a019defb64e9fe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376764"
---
# <a name="basic_ostream-class"></a>Класс basic_ostream

Этот шаблон класса описывает объект, который управляет вставкой элементов и закодированных объектов в буфер потока с `Elem`элементами типа , также известный как [char_type,](../standard-library/basic-ios-class.md#char_type)чьи черты характера определяются классом, `Tr`также известный как [traits_type.](../standard-library/basic-ios-class.md#traits_type)

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class Tr = char_traits<Elem>>
class basic_ostream : virtual public basic_ios<Elem, Tr>
```

### <a name="parameters"></a>Параметры

*Elem*\
`char_type`.

*Tr*\
`traits_type` символа.

## <a name="remarks"></a>Remarks

Большинство функций-членов, которые перегружают [operator<<](#basic_ostream_operator_lt_lt),  — это форматированные выходные функции. Они следуют этому шаблону:

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

Обе группы функций вызывают [setstate](../standard-library/basic-ios-class.md#setstate)**(badbit),** если они сталкиваются с сбоем при вставке элементов.

Объект класса basic_istream\< **Elem**, **Tr**> хранит только виртуальный открытый базовый объект класса [basic_ios](../standard-library/basic-ios-class.md)**\<Elem**, **Tr>**.

## <a name="example"></a>Пример

Дополнительные сведения о выходных потоках см. в примере для [класса basic_ofstream](../standard-library/basic-ofstream-class.md).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_ostream](#basic_ostream)|Формирует объект `basic_ostream`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[flush](#flush)|Очищает буфер.|
|[Положить](#put)|Помещает символ в поток.|
|[seekp](#seekp)|Сбрасывает позицию в потоке вывода.|
|[sentry](#sentry)|Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные выходные функции.|
|[Своп](#swap)|Меняет местами значения в этом объекте `basic_ostream` и значения предоставленного объекта `basic_ostream`.|
|[tellp](#tellp)|Сообщает позицию в потоке вывода.|
|[Написать](#write)|Помещает символы в поток.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператора](#op_eq)|Присваивает значение указанного параметра объекта `basic_ostream` этому объекту.|
|[оператор<<](#basic_ostream_operator_lt_lt)|Записывает данные в поток.|

## <a name="requirements"></a>Требования

**Заголовок:** \<ostream>

**Пространство имен:** std

## <a name="basic_ostreambasic_ostream"></a><a name="basic_ostream"></a>basic_ostream:::basic_ostream

Формирует объект `basic_ostream`.

```cpp
explicit basic_ostream(
    basic_streambuf<Elem, Tr>* strbuf,
    bool _Isstd = false);

basic_ostream(basic_ostream&& right);
```

### <a name="parameters"></a>Параметры

*strbuf*\
Объект типа [basic_streambuf](../standard-library/basic-streambuf-class.md).

*_Isstd*\
**верно,** если это стандартный поток; в противном случае, **ложные**.

*Правильно*\
Ссылка rvalue на объект типа `basic_ostream`.

### <a name="remarks"></a>Remarks

Первый конструктор инициализирует базовый класс, вызывая [init](../standard-library/basic-ios-class.md#init)().`strbuf` Второй конструктор инициализирует базовый класс, позвонив [basic_ios::Move](../standard-library/basic-ios-class.md#move)`(right)`.

### <a name="example"></a>Пример

Дополнительные сведения о выходных потоках см. в примере для [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream).

## <a name="basic_ostreamflush"></a><a name="flush"></a>basic_ostream::flush

Очищает буфер.

```cpp
basic_ostream<Elem, Tr>& flush();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект basic_ostream.

### <a name="remarks"></a>Remarks

Если [rdbuf](../standard-library/basic-ios-class.md#rdbuf) не является пустым указателем, функция вызывает **rdbuf->**[pubsync](../standard-library/basic-streambuf-class.md#pubsync). Если возвращается значение –1, функция вызывает [setstate](../standard-library/basic-ios-class.md#setstate)(**badbit**). Он ** \*** возвращает это .

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

## <a name="basic_ostreamoperatorltlt"></a><a name="basic_ostream_operator_lt_lt"></a>basic_ostream::оператор&lt;&lt;

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

*Pfn*\
Указатель функции.

*strbuf*\
Указатель на объект `stream_buf`.

*Валь*\
Элемент, записываемый в поток.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект basic_ostream.

### <a name="remarks"></a>Remarks

Заголовок \<> также определяет несколько глобальных операторов вставки. Для получения дополнительной информации см [<<. ](../standard-library/ostream-operators.md#op_lt_lt)

Функция первого члена гарантирует, что `ostr << endl` выражение формы вызывает [эндл](../standard-library/ostream-functions.md#endl)**(ostr) ,** а затем возвращает ** \*это.** Вторая и третья функции обеспечивают аналогичное поведение других манипуляторов, таких как [hex](../standard-library/ios-functions.md#hex). Все остальные функции являются форматированными выходными функциями.

Функция

```cpp
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```

извлекает элементы из *strbuf,* если *strbuf* не является нулевой указатель, и вставляет их. Извлечение останавливается в конце файла или если оно создает исключение (которое создается повторно). Оно также останавливается без извлечения соответствующего элемента, если вставка завершается неудачно. Если функция не вставляет элементы или если вставка создает исключение, эта функция вызывает [setstate](../standard-library/basic-ios-class.md#setstate)(**failbit**). В любом случае функция возвращает ** \*это.**

Функция

```cpp
basic_ostream<Elem, Tr>& operator<<(bool val);
```

преобразует `_Val` сятвик и вставляет его, позвонив [use_facet](../standard-library/basic-filebuf-class.md#open) **<num_put\<Элем, OutIt>** `(` [getloc](../standard-library/ios-base-class.md#getloc)). [put](#put)(**OutIt**([rdbuf](../standard-library/basic-ios-class.md#rdbuf)), **\*this**, `getloc`, **val**). Здесь, `OutIt` определяется как [ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md)**\<Элем, Tr>**. Функция возвращает ** \*это**.

Функции

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

каждый конвертировать *Валь* в числовом поле и вставить его,`getloc`позвонив use_facet<**num_put\<Elem, OutIt>**( ). **положить**(**OutIt**`rdbuf`( `getloc`, ** \*это**, **Валь**). Здесь **OutIt** определяется как **ostreambuf_iterator\<Elem, Tr>**. Функция возвращает ** \*это**.

Функции

```cpp
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```

каждый конвертировать *Валь* в числовом поле и вставить его,`getloc`позвонив use_facet<`getloc`num_put **\<Elem, OutIt>**(**) положить**(**OutIt**(`rdbuf`, ** \*это**, **валь**). Здесь **OutIt** определяется как **ostreambuf_iterator\<Elem, Tr>**. Функция возвращает ** \*это**.

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

## <a name="basic_ostreamoperator"></a><a name="op_eq"></a>basic_ostream:оператор

Присваивает значения указанного параметра объекта `basic_ostream` этому объекту.

```cpp
basic_ostream& operator=(basic_ostream&& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Ссылка `rvalue` на объект `basic_ostream`.

### <a name="remarks"></a>Remarks

Оператор-член вызывает swap `(right)`.

## <a name="basic_ostreamput"></a><a name="put"></a>basic_ostream::put

Помещает символ в поток.

```cpp
basic_ostream<Elem, Tr>& put(char_type _Ch);
```

### <a name="parameters"></a>Параметры

*_ch*\
Символ.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект basic_ostream.

### <a name="remarks"></a>Remarks

Неформатная функция вывода вставляет элемент *_Ch.* Он ** \*** возвращает это .

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

## <a name="basic_ostreamseekp"></a><a name="seekp"></a>basic_ostream::seekp

Сбрасывает позицию в выходном потоке.

```cpp
basic_ostream<Elem, Tr>& seekp(pos_type _Pos);

basic_ostream<Elem, Tr>& seekp(off_type _Off, ios_base::seekdir _Way);
```

### <a name="parameters"></a>Параметры

*_Pos*\
Позиция в потоке.

*_off*\
Смещение по отношению к *_Way*.

*_Way*\
Одно из перечислений [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir).

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект basic_ostream.

### <a name="remarks"></a>Remarks

Если [сбой](../standard-library/basic-ios-class.md#fail) **является ложным,** первый член функции вызывает **newpos и** [rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekpos](../standard-library/basic-streambuf-class.md#pubseekpos)(*_Pos),* для некоторых `pos_type` временных объектов `newpos`. Если `fail` это неверно, вторая функция вызывает **newpos и rdbuf->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)*(_Off, _Way).* В любом случае,`off_type`если ( )`off_type`**newpos (** ) (-1) (операция позиционирования не удается), то функция вызывает **istr.** [setstate](../standard-library/basic-ios-class.md#setstate)**(failbit**). Обе функции вернуть ** \*это**.

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

## <a name="basic_ostreamsentry"></a><a name="sentry"></a>basic_ostream::sentry

Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные выходные функции.

класс часовой : явный\<часовой (basic_ostream Элем, Tr>& _Ostr); оператор bool () Const; "sentry();

### <a name="remarks"></a>Remarks

Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные выходные функции. Если **ostr.**[good](../standard-library/basic-ios-class.md#good) имеет значение **true**, и **ostr.**[tie](../standard-library/basic-ios-class.md#tie) не является пустым указателем, конструктор вызывает **ostr.tie->**[flush](#flush). Конструктор затем хранит значение, `ostr.good` возвращенное в `status`. Более поздний `operator bool` вызов для доставки этого сохраненного значения.

Если `uncaught_exception` возвращает **false** и [flags](../standard-library/ios-base-class.md#flags) **&** [unitbuf](../standard-library/ios-functions.md#unitbuf) не равно нулю, деструктор вызывает [flush](#flush).

## <a name="basic_ostreamswap"></a><a name="swap"></a>basic_ostream::swap

Меняет местами значения в этом объекте `basic_ostream` и значения предоставленного объекта `basic_ostream`.

```cpp
void swap(basic_ostream& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Ссылка на объект `basic_ostream`.

### <a name="remarks"></a>Remarks

Функция участника вызывает [basic_ios::swap](../standard-library/basic-ios-class.md#swap) `(right)` для обмена содержимого этого объекта на содержимое *права.*

## <a name="basic_ostreamtellp"></a><a name="tellp"></a>basic_ostream::tellp

Сообщает позицию в выходном потоке.

```cpp
pos_type tellp();
```

### <a name="return-value"></a>Возвращаемое значение

Позиция в выходном потоке.

### <a name="remarks"></a>Remarks

Если [сбой](../standard-library/basic-ios-class.md#fail) **является ложным,** функция участника возвращает [rdbuf](../standard-library/basic-ios-class.md#rdbuf) **->** [pubseekoff](../standard-library/basic-streambuf-class.md#pubseekoff)(0, `cur`, **в**). В противном случае она возвращает `pos_type`(–1).

### <a name="example"></a>Пример

Пример использования `tellp` см. в разделе [seekp](#seekp).

## <a name="basic_ostreamwrite"></a><a name="write"></a>basic_ostream::написать

Помещает символы в поток.

```cpp
basic_ostream<Elem, Tr>& write(const char_type* str, streamsize count);
```

### <a name="parameters"></a>Параметры

*Рассчитывать*\
Количество символов для помещения в поток.

*Ул*\
Символы для помещения в поток.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на объект basic_ostream.

### <a name="remarks"></a>Remarks

[Неформатная функция вывода](../standard-library/basic-ostream-class.md) вставляет последовательность элементов *подсчета,* начиная с *str.*

### <a name="example"></a>Пример

Пример использования `write` см. в разделе [streamsize](../standard-library/ios-typedefs.md#streamsize).

## <a name="see-also"></a>См. также раздел

[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[программирование йострима](../standard-library/iostream-programming.md)\
[iostreams Конвенций](../standard-library/iostreams-conventions.md)
