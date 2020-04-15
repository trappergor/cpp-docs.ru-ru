---
title: Класс basic_istream
ms.date: 11/04/2016
f1_keywords:
- istream/std::basic_istream
- istream/std::basic_istream::gcount
- istream/std::basic_istream::get
- istream/std::basic_istream::getline
- 'istream/std::basic_istream::'
- istream/std::basic_istream::peek
- istream/std::basic_istream::putback
- istream/std::basic_istream::read
- istream/std::basic_istream::readsome
- istream/std::basic_istream::seekg
- istream/std::basic_istream::sentry
- istream/std::basic_istream::swap
- istream/std::basic_istream::sync
- istream/std::basic_istream::tellg
- istream/std::basic_istream::unget
helpviewer_keywords:
- std::basic_istream [C++]
- std::basic_istream [C++], gcount
- std::basic_istream [C++], get
- std::basic_istream [C++], getline
- std::basic_istream [C++], OVERWRITE
- std::basic_istream [C++], peek
- std::basic_istream [C++], putback
- std::basic_istream [C++], read
- std::basic_istream [C++], readsome
- std::basic_istream [C++], seekg
- std::basic_istream [C++], sentry
- std::basic_istream [C++], swap
- std::basic_istream [C++], sync
- std::basic_istream [C++], tellg
- std::basic_istream [C++], unget
ms.assetid: c7c27111-de6d-42b4-95a3-a7e65259bf17
ms.openlocfilehash: 03a6e3a65d6dc8c2fa896949855bd23a01578e5a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376829"
---
# <a name="basic_istream-class"></a>Класс basic_istream

Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока с элементами типа `Char_T`, также называемого [char_type](../standard-library/basic-ios-class.md#char_type). Их признаки символов определяются классом *Tr*, также называемым [traits_type](../standard-library/basic-ios-class.md#traits_type).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Char_T, class Tr = char_traits<Char_T>>
class basic_istream : virtual public basic_ios<Char_T, Tr>
```

## <a name="remarks"></a>Remarks

Большинство функций-членов, которые перегружают [оператор>>](#op_gt_gt), — это форматированные входные функции. Они следуют этому шаблону:

```cpp
iostate state = goodbit;
const sentry ok(*this);

if (ok)
{
    try
    {
        /*extract elements and convert
            accumulate flags in state.
            store a successful conversion*/
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);

return (*this);
```

Многие другие функции-члены — это неформатированные входные функции. Они следуют этому шаблону:

```cpp
iostate state = goodbit;
count = 0;    // the value returned by gcount
const sentry ok(*this, true);

if (ok)
{
    try
    {
        /* extract elements and deliver
            count extracted elements in count
            accumulate flags in state */
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);
```

Обе группы [`setstate`](../standard-library/basic-ios-class.md#setstate) `(eofbit)` функций вызываются, если они сталкиваются с концом файла при извлечении элементов.

Объект классовых `basic_istream<Char_T, Tr>` магазинов:

- Виртуальный общественный базовый объект класса [`basic_ios`](../standard-library/basic-ios-class.md) `<Char_T, Tr>`.

- Количество извлечения для последней неформатированной операции ввода (называемой `count` в предыдущем коде).

## <a name="example"></a>Пример

Подробнее о входных потоках см. в примере для [класса basic_ifstream](../standard-library/basic-ifstream-class.md).

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_istream](#basic_istream)|Создает объект типа `basic_istream`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[gcount](#gcount)|Возвращает число символов, считанных во время последнего неформатированного ввода.|
|[get](#get)|Считывает один или несколько символов из входного потока.|
|[getline](#getline)|Считывает строку из входного потока.|
|[Игнорировать](#ignore)|Пропускает несколько элементов после текущей позиции чтения.|
|[Заглянуть](#peek)|Возвращает следующий символ для чтения.|
|[putback](#putback)|Помещает указанный символ в поток.|
|[Прочитать](#read)|Считывает указанное количество символов из потока и сохраняет их в массиве.|
|[readsome](#readsome)|Чтение только из буфера.|
|[seekg](#seekg)|Перемещает позицию чтения в потоке.|
|[sentry](#sentry)|Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные входные функции.|
|[Своп](#swap)|Меняет местами этот объект `basic_istream` с указанным параметром объекта `basic_istream`.|
|[Синхронизации](#sync)|Синхронизирует связанное устройство ввода потока с буфером потока.|
|[tellg](#tellg)|Сообщает текущую позицию чтения в потоке.|
|[unget](#unget)|Помещает самый последний считанный символ обратно в поток.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператор>>](#op_gt_gt)|Вызывает функцию для входного потока или считывает форматированные данные из входного потока.|
|[оператора](#op_eq)|Назначает `basic_istream` справа от оператора этому объекту. Это задание перемещения, включающее ссылку, `rvalue` которая не оставляет копию позади.|

## <a name="requirements"></a>Требования

**Заголовок:** \<istream>

**Пространство имен:** std

## <a name="basic_istreambasic_istream"></a><a name="basic_istream"></a>basic_istream::basic_istream

Создает объект типа `basic_istream`.

```cpp
explicit basic_istream(
    basic_streambuf<Char_T, Tr>* strbuf,
    bool _Isstd = false);

basic_istream(basic_istream&& right);
```

### <a name="parameters"></a>Параметры

*strbuf*\
Объект типа [basic_streambuf](../standard-library/basic-streambuf-class.md).

*_Isstd*\
**правда,** если это стандартный поток; в противном случае, **ложные**.

*Правильно*\
Объект `basic_istream` для копирования.

### <a name="remarks"></a>Remarks

Первый конструктор инициализирует базовый класс, вызывая [`init`](../standard-library/basic-ios-class.md#init) `(strbuf)`. Он также хранит нуль в счетчике извлечений. Более подробную информацию об этом количестве извлечений можно ознакомьтесь с разделом «Замечания» обзора [basic_istream класса.](../standard-library/basic-istream-class.md)

Второй конструктор инициализирует базовый класс путем вызова `move(right)`. Он также `right.gcount()` хранит в отсчете извлечения и хранит zero в отсчете извлечения для «правильно».

### <a name="example"></a>Пример

Дополнительные сведения о входных потоках см. в примере для [класса basic_ifstream](../standard-library/basic-ifstream-class.md#basic_ifstream).

## <a name="basic_istreamgcount"></a><a name="gcount"></a>basic_istream::gcount

Возвращает число символов, считанных во время последнего неформатированного ввода.

```cpp
streamsize gcount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Счетчик извлечений.

### <a name="remarks"></a>Remarks

Используйте [basic_istream::get](#get) для чтения символов без форматирования.

### <a name="example"></a>Пример

```cpp
// basic_istream_gcount.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   cout << "Type the letter 'a': ";

   ws( cin );
   char c[10];

   cin.get( &c[0],9 );
   cout << c << endl;

   cout << cin.gcount( ) << endl;
}
```

```Input
a
```

```Output
Type the letter 'a': a
1
```

## <a name="basic_istreamget"></a><a name="get"></a>basic_istream::get

Считывает один или несколько символов из входного потока.

```cpp
int_type get();

basic_istream<Char_T, Tr>& get(Char_T& Ch);
basic_istream<Char_T, Tr>& get(Char_T* str, streamsize count);
basic_istream<Char_T, Tr>& get(Char_T* str, streamsize count, Char_T delimiter);

basic_istream<Char_T, Tr>& get(basic_streambuf<Char_T, Tr>& strbuf);
basic_istream<Char_T, Tr>& get(basic_streambuf<Char_T, Tr>& strbuf, Char_T delimiter);
```

### <a name="parameters"></a>Параметры

*Рассчитывать*\
Число символов для чтения из *strbuf*.

*Разделитель*\
Персонаж, который должен прекратить чтение, если он столкнулся до *подсчета*.

*Ул*\
Строка, в которую должна выполняться запись.

*Ch*\
Символ для получения.

*strbuf*\
Буфер, в который должна выполняться запись.

### <a name="return-value"></a>Возвращаемое значение

Форма get без параметров возвращает чтение элементов как целое число либо конец файла. Прочие формы возвращают поток (* `this`).

### <a name="remarks"></a>Remarks

Первая неформатная функция ввода извлекает элемент, если `rdbuf->sbumpc`это возможно, как бы возвращаясь. В противном `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof)случае, он возвращается . Если функция не извлекает элемент, она вызывает [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`.

Вторая функция извлекает элемент [int_type](../standard-library/basic-ios-class.md#int_type)`meta` таким же образом. Если `meta` сравнивается `traits_type::eof`с, функция `setstate(failbit)`вызывает . В противном `traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(meta)` случае, он хранит в *Ch*. Функция возвращает __«это__.

Третья функция `get(str, count, widen('\n'))`возвращается.

Четвертая функция извлекает `count - 1` до элементов и хранит их в массиве, начиная с *str.* Она всегда сохраняет `char_type` после сохранения всех извлеченных элементов. В целях тестирования извлечение останавливается:

- в конце файла;

- После функции извлекает элемент, который сравнивается с *делимитетом.* В этом случае элемент возвращается в контролируемую последовательность.

- После функции `count - 1` извлекает элементы.

Если функция не извлекает ни один элемент, она вызывает `setstate(failbit)`. В любом случае, он возвращает __это__.

Пятая функция `get(strbuf, widen('\n'))`возвращается .

Шестая функция извлекает элементы и вставляет их в *strbuf*. Извлечение останавливается на конце файла или на элементе, который сравнивается с *делимитером,* который не добывается. Оно также останавливается без извлечения соответствующего элемента, если вставка завершается неудачно или создает исключение (которое перехватывается, но не создается повторно). Если функция не извлекает ни один элемент, она вызывает `setstate(failbit)`. В любом случае функция возвращает __эту функцию__.

### <a name="example"></a>Пример

```cpp
// basic_istream_get.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10];

   c[0] = cin.get( );
   cin.get( c[1] );
   cin.get( &c[2],3 );
   cin.get( &c[4], 4, '7' );

   cout << c << endl;
}
```

```Output
1111
```

## <a name="basic_istreamgetline"></a><a name="getline"></a>basic_istream::getline

Получает строку из входного потока.

```cpp
basic_istream<Char_T, Tr>& getline(
    char_type* str,
    streamsize count);

basic_istream<Char_T, Tr>& getline(
    char_type* str,
    streamsize count,
    char_type delimiter);
```

### <a name="parameters"></a>Параметры

*Рассчитывать*\
Число символов для чтения из *strbuf*.

*Разделитель*\
Персонаж, который должен прекратить чтение, если он столкнулся до *подсчета*.

*Ул*\
Строка, в которую должна выполняться запись.

### <a name="return-value"></a>Возвращаемое значение

Поток __(это__).

### <a name="remarks"></a>Remarks

Первая из этих неформатных `getline(str, count, widen('\n'))`входных функций возвращается.

Вторая функция извлекает `count - 1` до элементов и хранит их в массиве, начиная с *str.* Она всегда сохраняет символ окончания строки после сохранения всех извлеченных элементов. В целях тестирования извлечение останавливается:

- в конце файла;

- После функции извлекает элемент, который сравнивается с *делимитетом.* В этом случае элемент не возвращается, и он не придатим к контролируемой последовательности.

- После функции `count - 1` извлекает элементы.

Если функция не извлекает `count - 1` элементов [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`или элементов, она вызывает . В любом случае, он возвращает __это__.

### <a name="example"></a>Пример

```cpp
// basic_istream_getline.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10];

   cin.getline( &c[0], 5, '2' );
   cout << c << endl;
}
```

```Output
121
```

## <a name="basic_istreamignore"></a><a name="ignore"></a>basic_istream::игнорировать

Пропускает несколько элементов после текущей позиции чтения.

```cpp
basic_istream<Char_T, Tr>& ignore(
    streamsize count = 1,
    int_type delimiter = traits_type::eof());
```

### <a name="parameters"></a>Параметры

*Рассчитывать*\
Количество пропускаемых элементов от текущей позиции чтения.

*Разделитель*\
Элемент, который, если он `ignore` столкнулся до подсчета голосов, приводит к возвращению и позволяет читать все элементы после *делимитеда.*

### <a name="return-value"></a>Возвращаемое значение

Поток __(это__).

### <a name="remarks"></a>Remarks

Функция неформатного ввода извлекает до *подсчета* элементов и отбрасывает их. Если *считать* `numeric_limits<int>::max`равно, однако, это принято как произвольно большой. Извлечение останавливается на ранней `Ch` стадии файла или на элементе, `traits_type::` [`to_int_type`](../standard-library/char-traits-struct.md#to_int_type) `(Ch)` который сравнивается с *делимитером* (который также добывается). Функция возвращает __«это__.

### <a name="example"></a>Пример

```cpp
// basic_istream_ignore.cpp
// compile with: /EHsc
#include <iostream>
int main( )
{
   using namespace std;
   char chararray[10];
   cout << "Type 'abcdef': ";
   cin.ignore( 5, 'c' );
   cin >> chararray;
   cout << chararray;
}
```

```Output
Type 'abcdef': abcdef
def
```

## <a name="basic_istreamoperator"></a><a name="op_gt_gt"></a>основной\_istream::оператор>>

Вызывает функцию для входного потока или считывает форматированные данные из входного потока.

```cpp
basic_istream& operator>>(basic_istream& (* Pfn)(basic_istream&));
basic_istream& operator>>(ios_base& (* Pfn)(ios_base&));
basic_istream& operator>>(basic_ios<Char_T, Tr>& (* Pfn)(basic_ios<Char_T, Tr>&));
basic_istream& operator>>(basic_streambuf<Char_T, Tr>* strbuf);
basic_istream& operator>>(bool& val);
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val);
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val);
basic_istream& operator>>(void *& val);
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

### <a name="parameters"></a>Параметры

*Pfn*\
Указатель функции.

*strbuf*\
Объект типа `stream_buf`.

*Валь*\
Значение для чтения из потока.

### <a name="return-value"></a>Возвращаемое значение

Поток __(это__).

### <a name="remarks"></a>Remarks

Заголовок \<istream> также определяет несколько глобальных операторов добычи. Дополнительные сведения см. в разделе [оператор>> (\<istream>)](../standard-library/istream-operators.md#op_gt_gt).

Функция первого члена гарантирует, что `istr >> ws` выражение [`ws`](../standard-library/istream-functions.md#ws) `(istr)`формы вызывает, а затем возвращает __это__. Вторая и третья функции гарантируют, [`hex`](../standard-library/ios-functions.md#hex)что другие манипуляторы, такие как, ведут себя аналогичным образом. Остальные функции являются отформатированными функциями ввода.

Функция:

```cpp
basic_istream& operator>>(
    basic_streambuf<Char_T, Tr>* strbuf);
```

извлекает элементы, если *strbuf* не является нулевой указатель, и вставляет их в *strbuf*. Извлечение останавливается в конце файла. Оно также останавливается без извлечения соответствующего элемента, если вставка завершается неудачно, или создает исключение (которое перехватывается, но не создается повторно). Если функция не извлекает элементов, она вызывает [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`. В любом случае функция возвращает __эту функцию__.

Функция:

```cpp
basic_istream& operator>>(bool& val);
```

извлекает поле и преобразует его в значение [`use_facet`](../standard-library/basic-filebuf-class.md#open) `< num_get<Char_T, InIt>(` [`getloc`](../standard-library/ios-base-class.md#getloc) `).` [`get`](../standard-library/ios-base-class.md#getloc) `( InIt(` [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) `), Init(0), *this, getloc, val)`Boolean, позвонив . Здесь `InIt` определяется [`istreambuf_iterator`](../standard-library/istreambuf-iterator-class.md) `<Char_T, Tr>`как . Функция возвращает __«это__.

Каждая из функций:

```cpp
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val);
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val);
basic_istream& operator>>(void *& val);
```

извлечь поле и преобразовать его в `use_facet<num_get<Char_T, InIt>(getloc).` [`get`](#get) `(InIt(rdbuf), Init(0), *this, getloc, val)`числовое значение, позвонив. Здесь, `InIt` определяется `istreambuf_iterator<Char_T, Tr>`как , и *Валь* имеет тип **долго,** **неподписанный долго,** или **недействительным** <strong>\*</strong> по мере необходимости.

Если преобразованное значение не может быть представлено как [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`тип *val,* функция вызывает. В любом случае функция возвращает __эту функцию__.

Каждая из функций:

```cpp
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```

извлечь поле и преобразовать его в `use_facet<num_get<Char_T, InIt>(getloc).get(InIt(rdbuf), Init(0), *this, getloc, val)`числовое значение, позвонив. Здесь, `InIt` определяется `istreambuf_iterator<Char_T, Tr>`как , и *Валь* имеет тип **двойной** или **длинный двойной** по мере необходимости.

Если преобразованное значение не может быть представлено как `setstate(failbit)`тип *val,* функция вызывает. В любом случае, он возвращает __это__.

### <a name="example"></a>Пример

```cpp
// istream_basic_istream_op_is.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

ios_base& hex2( ios_base& ib )
{
   ib.unsetf( ios_base::dec );
   ib.setf( ios_base::hex );
   return ib;
}

basic_istream<char, char_traits<char> >& somefunc(basic_istream<char, char_traits<char> > &i)
{
   if ( i == cin )
   {
      cerr << "i is cin" << endl;
   }
   return i;
}

int main( )
{
   int i = 0;
   cin >> somefunc;
   cin >> i;
   cout << i << endl;
   cin >> hex2;
   cin >> i;
   cout << i << endl;
}
```

## <a name="basic_istreamoperator"></a><a name="op_eq"></a>basic_istream::оператор

Назначает `basic_istream` справа от оператора этому объекту. Это задание перемещения, включающее ссылку, `rvalue` которая не оставляет копию позади.

```cpp
basic_istream& operator=(basic_istream&& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Ссылка `rvalue` на объект `basic_ifstream`.

### <a name="return-value"></a>Возвращаемое значение

Возвращает __»это__.

### <a name="remarks"></a>Remarks

Оператор-член `swap(right)`звонит .

## <a name="basic_istreampeek"></a><a name="peek"></a>basic_istream::p

Возвращает следующий символ для чтения.

```cpp
int_type peek();
```

### <a name="return-value"></a>Возвращаемое значение

Следующий символ для чтения.

### <a name="remarks"></a>Remarks

Неформатная функция ввода извлекает элемент, если это `rdbuf->` [`sgetc`](../standard-library/basic-streambuf-class.md#sgetc)возможно, как бы возвращаясь. В противном `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof)случае, он возвращается .

### <a name="example"></a>Пример

```cpp
// basic_istream_peek.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2;
   cout << "Type 'abcde': ";

   c2 = cin.peek( );
   cin.getline( &c[0], 9 );

   cout << c2 << " " << c << endl;
}
```

```Input
abcde
```

```Output
Type 'abcde': abcde
a abcde
```

## <a name="basic_istreamputback"></a><a name="putback"></a>basic_istream::p

Помещает указанный символ в поток.

```cpp
basic_istream<Char_T, Tr>& putback(
    char_type Ch);
```

### <a name="parameters"></a>Параметры

*Ch*\
Символ для помещения обратно в поток.

### <a name="return-value"></a>Возвращаемое значение

Поток __(это__).

### <a name="remarks"></a>Remarks

Неформатная [функция ввода](../standard-library/basic-istream-class.md) возвращает *Ch,* если это [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) `->` [`sputbackc`](../standard-library/basic-streambuf-class.md#sputbackc)возможно, как будто позвонив. Если `rdbuf` это нулевая указка, `sputbackc` `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof)или если [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)`вызов возвращается, функция вызывает . В любом случае, он возвращает __это__.

### <a name="example"></a>Пример

```cpp
// basic_istream_putback.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2, c3;

   c2 = cin.get( );
   c3 = cin.get( );
   cin.putback( c2 );
   cin.getline( &c[0], 9 );
   cout << c << endl;
}
```

```Output
qwq
```

## <a name="basic_istreamread"></a><a name="read"></a>basic_istream::read

Считывает указанное количество символов из потока и сохраняет их в массиве.

Этот метод является потенциально опасным, так как зависит от вызывающего объекта при проверке правильности переданных значений.

```cpp
basic_istream<Char_T, Tr>& read(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>Параметры

*Ул*\
Массив, из которого должны считываться символы.

*Рассчитывать*\
Число символов для чтения.

### <a name="return-value"></a>Возвращаемое значение

Поток ( `*this`).

### <a name="remarks"></a>Remarks

Неформатная функция ввода извлекает до *подсчитывая* элементы и хранит их в массиве, начиная с *str.* Извлечение останавливается на ранней стадии [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`файла, и в этом случае функция вызывает. В любом случае, он возвращает __это__.

### <a name="example"></a>Пример

```cpp
// basic_istream_read.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main()
{
    char c[10];
    int count = 5;

    cout << "Type 'abcde': ";

    // Note: cin::read is potentially unsafe, consider
    // using cin::_Read_s instead.
    cin.read(&c[0], count);
    c[count] = 0;

    cout << c << endl;
}
```

```Input
abcde
```

```Output
Type 'abcde': abcde
abcde
```

## <a name="basic_istreamreadsome"></a><a name="readsome"></a>basic_istream::readsome

Считывает указанное число значений символов.

Этот метод является потенциально опасным, так как зависит от вызывающего объекта при проверке правильности переданных значений.

```cpp
streamsize readsome(
    char_type* str,
    streamsize count);
```

### <a name="parameters"></a>Параметры

*Ул*\
Массив, в котором `readsome` сохраняет символы, которые считывает.

*Рассчитывать*\
Число символов для чтения.

### <a name="return-value"></a>Возвращаемое значение

Количество символов на самом [`gcount`](#gcount)деле читать, .

### <a name="remarks"></a>Remarks

Эта неформатная функция ввода извлекает *элементы* из входному потока и хранит их в *стр.*

Эта функция не ожидает входных данных. Она считывает все доступные данные.

### <a name="example"></a>Пример

```cpp
// basic_istream_readsome.cpp
// compile with: /EHsc /W3
#include <iostream>
using namespace std;

int main( )
{
   char c[10];
   int count = 5;

   cout << "Type 'abcdefgh': ";

   // cin.read blocks until user types input.
   // Note: cin::read is potentially unsafe, consider
   // using cin::_Read_s instead.
   cin.read(&c[0], 2);

   // Note: cin::readsome is potentially unsafe, consider
   // using cin::_Readsome_s instead.
   int n = cin.readsome(&c[0], count);  // C4996
   c[n] = 0;
   cout << n << " characters read" << endl;
   cout << c << endl;
}
```

## <a name="basic_istreamseekg"></a><a name="seekg"></a>basic_istream::seekg

Перемещает позицию чтения в потоке.

```cpp
basic_istream<Char_T, Tr>& seekg(pos_type pos);

basic_istream<Char_T, Tr>& seekg(off_type off, ios_base::seekdir way);
```

### <a name="parameters"></a>Параметры

*Pos*\
Абсолютное положение, в которое следует переместить указатель чтения.

*выключить*\
Смещение для перемещения указателя чтения относительно *пути.*

*Путь*\
Одно из перечислений [ios_base::seekdir](../standard-library/ios-base-class.md#seekdir).

### <a name="return-value"></a>Возвращаемое значение

Поток __(это__).

### <a name="remarks"></a>Remarks

Первая функция-член выполняет как абсолютный поиск, вторая функция-член выполняет относительный поиск.

> [!NOTE]
> Не используйте вторую функцию-член с текстовыми файлами, так как стандартный C++ не поддерживает относительный поиск в текстовых файлах.

Если [`fail`](../standard-library/basic-ios-class.md#fail) это неверно, первая функция участника вызывает, `newpos =` [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) `->` [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos) `(pos)`для некоторых `pos_type` временных объектов. `newpos` Если `fail` это неверно, `newpos = rdbuf->` [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) `( off, way)`вторая функция вызывает . В любом случае, `(off_type)newpos == (off_type)(-1)` если (операция позиционирования `istr.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`не удается), функция вызывает . Обе функции возвращают __«это__.

Если [`fail`](../standard-library/basic-ios-class.md#fail) это правда, функции участника ничего не делают.

### <a name="example"></a>Пример

```cpp
// basic_istream_seekg.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main ( )
{
   using namespace std;
   ifstream file;
   char c, c1;

   file.open( "basic_istream_seekg.txt" );
   file.seekg(2);   // seek to position 2
   file >> c;
   cout << c << endl;
}
```

## <a name="basic_istreamsentry"></a><a name="sentry"></a>basic_istream::sentry

Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные входные функции.

```cpp
class sentry {
   public:
   explicit sentry(
      basic_istream<Char_T, Tr>& _Istr,
      bool _Noskip = false);
   operator bool() const;
   };
```

### <a name="remarks"></a>Remarks

Если `_Istr.` [`good`](../standard-library/basic-ios-class.md#good) это правда, конструктор:

- Вызовы, `_Istr.` [`tie`](../standard-library/basic-ios-class.md#tie) `->` [`flush`](../standard-library/basic-ostream-class.md#flush) если `_Istr.tie` это не нулевая указатель.

- Эффективно [`ws`](../standard-library/istream-functions.md#ws) `(_Istr)` вызывает `_Istr.` [`flags`](../standard-library/ios-base-class.md#flags) `&` [`skipws`](../standard-library/ios-functions.md#skipws) если nonzero.

Если после любой `_Istr.good` такой подготовки, `_Istr.` [`setstate`](../standard-library/basic-ios-class.md#setstate) `(failbit)`является ложным, конструктор звонки . В любом случае, конструктор хранит значение, возвращенное `_Istr.good` в `status`. Более поздний `operator bool` вызов для доставки этого сохраненного значения.

## <a name="basic_istreamswap"></a><a name="swap"></a>basic_istream::swap

Меняет местами содержимое двух объектов `basic_istream`.

```cpp
void swap(basic_istream& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Ссылка lvalue на объект `basic_istream`.

### <a name="remarks"></a>Remarks

Вызовы функции [`basic_ios::swap`](../standard-library/basic-ios-class.md#swap) `(right)`участника . Он также обменивает количество добычи с отсчетом извлечения для *права.*

## <a name="basic_istreamsync"></a><a name="sync"></a>basic_istream::sync

Синхронизирует связанное устройство ввода потока с буфером потока.

```cpp
int sync();
```

### <a name="return-value"></a>Возвращаемое значение

Если [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) это нулевая указка, функция возвращается -1. В противном `rdbuf->` [`pubsync`](../standard-library/basic-streambuf-class.md#pubsync)случае, он вызывает . Если этот вызов возвращается -1, функция вызывает [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)` и возвращает -1. В противном случае функция возвращает нуль.

## <a name="basic_istreamtellg"></a><a name="tellg"></a>basic_istream::tellg

Сообщает текущую позицию чтения в потоке.

```cpp
pos_type tellg();
```

### <a name="return-value"></a>Возвращаемое значение

Текущая позиция в потоке.

### <a name="remarks"></a>Remarks

Если [`fail`](../standard-library/basic-ios-class.md#fail) функция необоснованна, функция участника возвращается. [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) `->` [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) `(0, cur, in)` В противном случае возвращается значение `pos_type(-1)`.

### <a name="example"></a>Пример

```cpp
// basic_istream_tellg.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main()
{
    using namespace std;
    ifstream file;
    char c;
    streamoff i;

    file.open("basic_istream_tellg.txt");
    i = file.tellg();
    file >> c;
    cout << c << " " << i << endl;

    i = file.tellg();
    file >> c;
    cout << c << " " << i << endl;
}
```

## <a name="basic_istreamunget"></a><a name="unget"></a>basic_istream::unget

Помещает самый последний считанный символ обратно в поток.

```cpp
basic_istream<Char_T, Tr>& unget();
```

### <a name="return-value"></a>Возвращаемое значение

Поток __(это__).

### <a name="remarks"></a>Remarks

Функция [неформатного ввода](../standard-library/basic-istream-class.md) возвращает предыдущий элемент в поток, если `rdbuf->` [`sungetc`](../standard-library/basic-streambuf-class.md#sungetc)это возможно, как бы вызывая. Если [`rdbuf`](../standard-library/basic-ios-class.md#rdbuf) это нулевая указка, `sungetc` `traits_type::` [`eof`](../standard-library/basic-ios-class.md#eof)или если [`setstate`](../standard-library/basic-ios-class.md#setstate) `(badbit)`вызов возвращается, функция вызывает . В любом случае, он возвращает __это__.

Для получения `unget` информации о [`basic_streambuf::sungetc`](../standard-library/basic-streambuf-class.md#sungetc)том, как может потерпеть неудачу, см.

### <a name="example"></a>Пример

```cpp
// basic_istream_unget.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

int main( )
{
   char c[10], c2;

   cout << "Type 'abc': ";
   c2 = cin.get( );
   cin.unget( );
   cin.getline( &c[0], 9 );
   cout << c << endl;
}
```

```Input
abc
```

```Output
Type 'abc': abc
abc
```

## <a name="see-also"></a>См. также раздел

[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[программирование йострима](../standard-library/iostream-programming.md)\
[iostreams Конвенций](../standard-library/iostreams-conventions.md)
