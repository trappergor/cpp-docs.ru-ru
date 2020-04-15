---
title: Класс basic_filebuf
ms.date: 11/04/2016
f1_keywords:
- fstream/std::basic_filebuf
- fstream/std::basic_filebuf::char_type
- fstream/std::basic_filebuf::int_type
- fstream/std::basic_filebuf::off_type
- fstream/std::basic_filebuf::pos_type
- fstream/std::basic_filebuf::traits_type
- fstream/std::basic_filebuf::close
- fstream/std::basic_filebuf::is_open
- fstream/std::basic_filebuf::open
- fstream/std::basic_filebuf::overflow
- fstream/std::basic_filebuf::pbackfail
- fstream/std::basic_filebuf::seekoff
- fstream/std::basic_filebuf::seekpos
- fstream/std::basic_filebuf::setbuf
- fstream/std::basic_filebuf::Swap
- fstream/std::basic_filebuf::sync
- fstream/std::basic_filebuf::uflow
- fstream/std::basic_filebuf::underflow
helpviewer_keywords:
- std::basic_filebuf [C++]
- std::basic_filebuf [C++], char_type
- std::basic_filebuf [C++], int_type
- std::basic_filebuf [C++], off_type
- std::basic_filebuf [C++], pos_type
- std::basic_filebuf [C++], traits_type
- std::basic_filebuf [C++], close
- std::basic_filebuf [C++], is_open
- std::basic_filebuf [C++], open
- std::basic_filebuf [C++], overflow
- std::basic_filebuf [C++], pbackfail
- std::basic_filebuf [C++], seekoff
- std::basic_filebuf [C++], seekpos
- std::basic_filebuf [C++], setbuf
- std::basic_filebuf [C++], Swap
- std::basic_filebuf [C++], sync
- std::basic_filebuf [C++], uflow
- std::basic_filebuf [C++], underflow
ms.assetid: 3196ba5c-bf38-41bd-9a95-70323ddfca1a
ms.openlocfilehash: 35bed08f2495c971df7f79f62e32b3ff68dfb3d2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376884"
---
# <a name="basic_filebuf-class"></a>Класс basic_filebuf

Описывает буфер потока, который контролирует передачу элементов типа *Char_T,* черты характера которых определяются классом *Tr,* к и из последовательности элементов, хранящихся во внешнем файле.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Char_T, class Tr = char_traits<Char_T>>
class basic_filebuf : public basic_streambuf<Char_T, Tr>
```

### <a name="parameters"></a>Параметры

*Char_T*\
Базовый элемент буфера файла.

*Tr*\
Черты основного элемента буфера файла (обычно). `char_traits<Char_T>`

## <a name="remarks"></a>Remarks

Шаблон класса описывает буфер потока, который контролирует передачу элементов типа *Char_T,* черты характера которых определяются классом *Tr,* к и из последовательности элементов, хранящихся во внешнем файле.

> [!NOTE]
> Объекты `basic_filebuf` типа создаются с внутренним буфером `char_type` __\* символа__ типа независимо от указанного параметра типа *Char_T.* Это означает, что строка Unicode (содержащая **wchar_t** символы) будет преобразована в строку ANSI (содержащую **символы)** перед написанием во внутренний буфер. Для хранения строк Unicode в буфере создайте новый буфер [`basic_streambuf::pubsetbuf`](../standard-library/basic-streambuf-class.md#pubsetbuf) `()` типа **wchar_t** и установите его методом. Ниже приведен пример, демонстрирующий такие действия.

Объект класса `basic_filebuf<Char_T, Tr>` хранит указатель файла, который `FILE` обозначает объект, который управляет потоком, связанным с открытым файлом. Он также содержит указатели на два аспекта преобразования файла для использования защищенными функциями-членами [overflow](#overflow) и [underflow](#underflow). Для получения дополнительной [`basic_filebuf::open`](#open)информации см.

## <a name="example"></a>Пример

Следующий пример демонстрирует способ использования объекта типа `basic_filebuf<wchar_t>` для хранения символов Юникода в своем внутреннем буфере, с помощью метода `pubsetbuf()`.

```cpp
// unicode_basic_filebuf.cpp
// compile with: /EHsc

#include <iostream>
#include <string>
#include <fstream>
#include <iomanip>
#include <memory.h>
#include <string.h>

#define IBUFSIZE 16

using namespace std;

void hexdump(const string& filename);

int main()
{
    wchar_t* wszHello = L"Hello World";
    wchar_t wBuffer[128];

    basic_filebuf<wchar_t> wOutFile;

    // Open a file, wcHello.txt, then write to it, then dump the
    // file's contents in hex
    wOutFile.open("wcHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wcHello.txt\n";
        return -1;
    }
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "Hex Dump of wcHello.txt - note that output is ANSI chars:\n";
    hexdump(string("wcHello.txt"));

    // Open a file, wwHello.txt, then set the internal buffer of
    // the basic_filebuf object to be of type wchar_t, then write
    // to the file and dump the file's contents in hex
    wOutFile.open("wwHello.txt",
        ios_base::out | ios_base::trunc | ios_base::binary);
    if(!wOutFile.is_open())
    {
        cout << "Error Opening wwHello.txt\n";
        return -1;
    }
    wOutFile.pubsetbuf(wBuffer, (streamsize)128);
    wOutFile.sputn(wszHello, (streamsize)wcslen(wszHello));
    wOutFile.close();
    cout << "\nHex Dump of wwHello.txt - note that output is wchar_t chars:\n";
    hexdump(string("wwHello.txt"));

    return 0;
}

// dump contents of filename to stdout in hex
void hexdump(const string& filename)
{
    fstream ifile(filename.c_str(),
        ios_base::in | ios_base::binary);
    char *ibuff = new char[IBUFSIZE];
    char *obuff = new char[(IBUFSIZE*2)+1];
    int i;

    if(!ifile.is_open())
    {
        cout << "Cannot Open " << filename.c_str()
             << " for reading\n";
        return;
    }
    if(!ibuff || !obuff)
    {
        cout << "Cannot Allocate buffers\n";
        ifile.close();
        return;
    }

    while(!ifile.eof())
    {
        memset(obuff,0,(IBUFSIZE*2)+1);
        memset(ibuff,0,IBUFSIZE);
        ifile.read(ibuff,IBUFSIZE);

        // corner case where file is exactly a multiple of
        // 16 bytes in length
        if(ibuff[0] == 0 && ifile.eof())
            break;

        for(i = 0; i < IBUFSIZE; i++)
        {
            if(ibuff[i] >= ' ')
                obuff[i] = ibuff[i];
            else
                obuff[i] = '.';

            cout << setfill('0') << setw(2) << hex
                 << (int)ibuff[i] << ' ';
        }
        cout << "  " << obuff << endl;
    }
    ifile.close();
}
```

```Output
Hex Dump of wcHello.txt - note that output is ANSI chars:
48 65 6c 6c 6f 20 57 6f 72 6c 64 00 00 00 00 00   Hello World.....

Hex Dump of wwHello.txt - note that output is wchar_t chars:
48 00 65 00 6c 00 6c 00 6f 00 20 00 57 00 6f 00   H.e.l.l.o. .W.o.
72 00 6c 00 64 00 00 00 00 00 00 00 00 00 00 00   r.l.d...........
```

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_filebuf](#basic_filebuf)|Создает объект типа `basic_filebuf`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Связывает имя типа с параметром шаблона `Char_T`.|
|[int_type](#int_type)|Делает этот тип в области `basic_filebuf` эквивалентным типу с таким же именем в области `Tr`.|
|[off_type](#off_type)|Делает этот тип в области `basic_filebuf` эквивалентным типу с таким же именем в области `Tr`.|
|[pos_type](#pos_type)|Делает этот тип в области `basic_filebuf` эквивалентным типу с таким же именем в области `Tr`.|
|[traits_type](#traits_type)|Связывает имя типа с параметром шаблона `Tr`.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Закрыть](#close)|Закрывает файл.|
|[is_open](#is_open)|Указывает, открыт ли файл.|
|[open](#open)|Открывает файл.|
|[Переполнения](#overflow)|Защищенная виртуальная функция, которая может вызываться при вставке нового символа в полный буфер.|
|[pbackfail](#pbackfail)|Защищенная виртуальная функция-член пытается поместить элемент обратно во входной поток, затем делает его текущим (на него указывает следующий указатель).|
|[seekoff](#seekoff)|Защищенная виртуальная функция-член пытается изменить текущие положения управляемых потоков.|
|[seekpos](#seekpos)|Защищенная виртуальная функция-член пытается изменить текущие положения управляемых потоков.|
|[setbuf](#setbuf)|Защищенная виртуальная функция-член выполняет операции, относящиеся непосредственно к каждому производному буферу потока.|
|[Своп](#swap)|Меняет местами содержимое этого `basic_filebuf` и содержимое указанного параметра `basic_filebuf`.|
|[Синхронизации](#sync)|Защищенная виртуальная функция пытается синхронизировать управляемые потоки с любыми связанными внешними потоками.|
|[uflow](../standard-library/basic-streambuf-class.md#uflow)|Защищенная виртуальная функция для извлечения текущего элемента из входного потока.|
|[недотека](#underflow)|Защищенная виртуальная функция для извлечения текущего элемента из входного потока.|

## <a name="requirements"></a>Требования

**Заголовок:** \<fstream>

**Пространство имен:** std

## <a name="basic_filebufbasic_filebuf"></a><a name="basic_filebuf"></a>basic_filebuf::basic_filebuf

Создает объект типа `basic_filebuf`.

```cpp
basic_filebuf();

basic_filebuf(basic_filebuf&& right);
```

### <a name="remarks"></a>Remarks

Первый конструктор сохраняет пустой указатель во всех указателях, управляющих входным и выходным буферами. Он также сохраняет пустой указатель в указателе файла.

Второй конструктор инициализирует объект с содержимым *справа,* относился как ссылка на rvalue.

## <a name="basic_filebufchar_type"></a><a name="char_type"></a>basic_filebuf:char_type

Связывает имя типа с параметром шаблона `Char_T`.

```cpp
typedef Char_T char_type;
```

## <a name="basic_filebufclose"></a><a name="close"></a>basic_filebuf::закрыть

Закрывает файл.

```cpp
basic_filebuf<Char_T, Tr> *close();
```

### <a name="return-value"></a>Возвращаемое значение

Функция-член возвращает указатель null, если указатель файла является указателем null.

### <a name="remarks"></a>Remarks

`close` вызывает `fclose(fp)`. Если эта функция возвращает ненулевое значение, то возвращается пустой указатель. В противном случае возвращается **this**, чтобы указать, что файл был успешно закрыт.

Для широкого потока, если какие-либо вставки произошли с момента `streampos`открытия потока, [`overflow`](#overflow)или с момента последнего вызова к , функция вызывает . Он также вставляет любую последовательность, необходимую для восстановления `fac` исходного состояния преобразования, используя грань преобразования файла для вызова `fac.unshift` по мере необходимости. Каждый `byte` произведенный элемент **символа** типа пишется в связанный поток, обозначенный `fp` `fputc(byte, fp)`указателем файла, как будто последовательными вызовами формы. Если вызов `fac.unshift` или любой записи не удается, функция не удается.

### <a name="example"></a>Пример

Следующий пример предполагает два файла в текущем каталоге: *basic_filebuf_close.txt* (содержимое "тестирование") и *iotest.txt* (содержимое "ssss").

```cpp
// basic_filebuf_close.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main() {
   using namespace std;
   ifstream file;
   basic_ifstream <wchar_t> wfile;
   char c;
   // Open and close with a basic_filebuf
   file.rdbuf()->open( "basic_filebuf_close.txt", ios::in );
   file >> c;
   cout << c << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "iotest.txt" );
   file >> c;
   cout << c << endl;
   file.close( );

   // open a file with a wide character name
   wfile.open( L"iotest.txt" );

   // Open and close a nonexistent with a basic_filebuf
   file.rdbuf()->open( "ziotest.txt", ios::in );
   cout << file.fail() << endl;
   file.rdbuf( )->close( );

   // Open/close directly
   file.open( "ziotest.txt" );
   cout << file.fail() << endl;
   file.close( );
}
```

```Output
t
s
0
1
```

## <a name="basic_filebufint_type"></a><a name="int_type"></a>basic_filebuf::int_type

Делает этот `basic_filebuf` тип в пределах `Tr` сферы, эквивалентной типу одного и того же имени в области.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="basic_filebufis_open"></a><a name="is_open"></a>basic_filebuf::is_open

Указывает, открыт ли файл.

```cpp
bool is_open() const;
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если указатель файла не является недействительным.

### <a name="example"></a>Пример

```cpp
// basic_filebuf_is_open.cpp
// compile with: /EHsc
#include <fstream>
#include <iostream>

int main( )
{
   using namespace std;
   ifstream file;
   cout << boolalpha << file.rdbuf( )->is_open( ) << endl;

   file.open( "basic_filebuf_is_open.cpp" );
   cout << file.rdbuf( )->is_open( ) << endl;
}
```

```Output
false
true
```

## <a name="basic_filebufoff_type"></a><a name="off_type"></a>basic_filebuf:::off_type

Делает этот `basic_filebuf` тип в пределах `Tr` сферы, эквивалентной типу одного и того же имени в области.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="basic_filebufopen"></a><a name="open"></a>basic_filebuf::открыто

Открывает файл.

```cpp
basic_filebuf<Char_T, Tr> *open(
    const char* filename,
    ios_base::openmode mode,
    int protection = (int)ios_base::_Openprot);

basic_filebuf<Char_T, Tr> *open(
    const char* filename,
    ios_base::openmode mode);

basic_filebuf<Char_T, Tr> *open(
    const wchar_t* filename,
    ios_base::openmode mode,
    int protection = (int)ios_base::_Openprot);

basic_filebuf<Char_T, Tr> *open(
    const wchar_t* filename,
    ios_base::openmode mode);
```

### <a name="parameters"></a>Параметры

*Имени файла*\
Имя файла, который необходимо открыть.

*Режим*\
Один из перечислений в [`ios_base::openmode`](../standard-library/ios-base-class.md#openmode).

*Защиты*\
Защита открытия файла по умолчанию, эквивалентная параметру *sflag* в [_fsopen, _wfsopen.](../c-runtime-library/reference/fsopen-wfsopen.md)

### <a name="return-value"></a>Возвращаемое значение

Если буфер уже открыт, или если указатель файла является нулевой указателем, функция возвращает нулевую закательную. В противном случае возвращается **this**.

### <a name="remarks"></a>Remarks

Функция участника открывает файл с *именем файла,* вызывая [`fopen`](../c-runtime-library/reference/fopen-wfopen.md) `(filename, strmode)`. `strmode`определяется `mode & ~(` [`ate`](../standard-library/ios-base-class.md#openmode) `|` [`binary`](../standard-library/ios-base-class.md#openmode) `)`из:

- `ios_base::in`становится `"r"` (открыть существующий файл для чтения).

- [ios_base::out](../standard-library/ios-base-class.md#fmtflags) `ios_base::out | ios_base::trunc` or `"w"` becomes (truncate existing file or create for writing).

- `ios_base::out | app`становится `"a"` (открытый существующий файл для приложения всех записей).

- `ios_base::in | ios_base::out`становится `"r+"` (открытым существующим файлом для чтения и письма).

- `ios_base::in | ios_base::out | ios_base::trunc`становится `"w+"` (сужайте существующий файл или создайте для чтения и письма).

- `ios_base::in | ios_base::out | ios_base::app`становится `"a+"` (открыть существующий файл для чтения и для приложения всех записей).

Если `mode & ios_base::binary` функция незеро, `b` функция `strmode` пригоствия, чтобы открыть двоичный поток вместо текстового потока. Затем он хранит значение, `fopen` возвращенное `fp`в указатель файла. Если `mode & ios_base::ate` указатель файла не является указателем null, функция `fseek(fp, 0, SEEK_END)` призывает позиционировать поток в конце файла. Если эта операция позиционирования [`close`](#close) `(fp)` не справляется, функция вызывает и хранит указатель нулевой идентифицирующей стих в указателе файла.

Если указатель файла не является указателем null, функция определяет грань преобразования файла: `use_facet<codecvt<Char_T, char, traits_type::` [`state_type`](../standard-library/char-traits-struct.md#state_type) `> >(` [`getloc`](../standard-library/basic-streambuf-class.md#getloc) `)`, для использования [в потоке](#underflow) и [переполнении.](#overflow)

Если указатель файла является пустым, эта функция возвращает пустой указатель. В противном случае возвращается **this**.

### <a name="example"></a>Пример

Смотрите [`basic_filebuf::close`](#close) пример, который `open`использует .

## <a name="basic_filebufoperator"></a><a name="op_eq"></a>basic_filebuf::оператор

Назначьте содержимое этого объекта буфера потока. Это назначение хода, включающее rvalue, которая не оставляет копию позади.

```cpp
basic_filebuf& operator=(basic_filebuf&& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Ссылка rvalue на объект [basic_filebuf](../standard-library/basic-filebuf-class.md).

### <a name="return-value"></a>Возвращаемое значение

Возвращает __»это__.

### <a name="remarks"></a>Remarks

Оператор-член заменяет содержимое объекта, используя содержимое *права,* отнесемый к ссылке rvalue. Для получения дополнительной информации, [см. Rvalue ссылка декларатор:  &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="basic_filebufoverflow"></a><a name="overflow"></a>basic_filebuf::overflow

Вызывается при вставке нового символа в полный буфер.

```cpp
virtual int_type overflow(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Параметры

*_meta*\
Символ для вставки `traits_type::eof`в буфер или .

### <a name="return-value"></a>Возвращаемое значение

Если функция не может быть `traits_type::eof`успешной, она возвращается. В противном `traits_type::` [`not_eof`](../standard-library/char-traits-struct.md#not_eof) `(_Meta)`случае, он возвращается .

### <a name="remarks"></a>Remarks

Если `_Meta != traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof)защищенная функция виртуального члена пытается `ch = traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(_Meta)` вставить элемент в буфер вывода. Это можно сделать разными способами.

- Если позиция записи доступна, можно сохранить элемент в позиции записи и увеличить следующий указатель для выходного буфера.

- Можно сделать позицию записи доступной, выделяя новое или дополнительное хранилище для выходного буфера.

- Он может преобразовать любой ожидающий `ch`выход в буфер вывода, а затем, используя грань преобразования файла `fac` для вызова `fac.out` по мере необходимости. Каждый `ch` произведенный элемент *символа* типа пишется в связанный поток, обозначенный `fp` `fputc(ch, fp)`указателем файла, как будто последовательными вызовами формы. В случае сбоя любого преобразования или записи эта функция завершается неудачно.

## <a name="basic_filebufpbackfail"></a><a name="pbackfail"></a>basic_filebuf::pbackfail

Пытается поместить элемент обратно во входной поток, затем делает его текущим (на него указывает следующий указатель).

```cpp
virtual int_type pbackfail(int_type _Meta = traits_type::eof);
```

### <a name="parameters"></a>Параметры

*_meta*\
Символ для вставки в буфер или `traits_type::eof`.

### <a name="return-value"></a>Возвращаемое значение

Если функция не может быть `traits_type::eof`успешной, она возвращается. В противном `traits_type::` [`not_eof`](../standard-library/char-traits-struct.md#not_eof) `(_Meta)`случае, он возвращается .

### <a name="remarks"></a>Remarks

Защищенная виртуальная функция-член помещает элемент обратно во входной буфер, а затем делает его текущим (на него указывает следующий указатель). Если `_Meta == traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof)элемент для отодвига явки фактически является тем, который уже находится в потоке перед текущим элементом. В противном случае `ch = traits_type::` [`to_char_type`](../standard-library/char-traits-struct.md#to_char_type) `(_Meta)`этот элемент заменяется . Функция может передать элемент обратно различными способами.

- Если `putback` позиция доступна, и элемент, хранящийся там, сравнивается `ch`с, он может утилизировать следующий указатель для буфера ввода.

- Если функция может `putback` сделать позицию доступной, она может сделать это, установить `ch` следующий указатель, чтобы указать на это положение, и хранить в этом положении.

- Если функция может отодвинуть элемент на вхотозательный поток, `ungetc` она может сделать это, например, вызывая элемент **символа**типа.

## <a name="basic_filebufpos_type"></a><a name="pos_type"></a>basic_filebuf::pос-тип

Делает этот `basic_filebuf` тип в пределах `Tr` сферы, эквивалентной типу одного и того же имени в области.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="basic_filebufseekoff"></a><a name="seekoff"></a>basic_filebuf::seekoff

Пытается изменить текущие положения для управляемых потоков.

```cpp
virtual pos_type seekoff(
    off_type _Off,
    ios_base::seekdir _Way,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

*_off*\
Положение, чтобы искать относительно *_Way*.

*_Way*\
Начальная точка для операций смещения. Возможные значения см. в разделе [seekdir](../standard-library/ios-base-class.md#seekdir).

*_which*\
Задает режим для положения указателя. По умолчанию разрешается изменять позиции чтения и записи.

### <a name="return-value"></a>Возвращаемое значение

Возвращает новую позицию или недопустимую позицию потока.

### <a name="remarks"></a>Remarks

Защищенная функция виртуального члена пытается изменить текущие позиции для контролируемых потоков. Для объекта класса [`basic_filebuf`](../standard-library/basic-filebuf-class.md) `<Char_T, Tr>`позиция потока может быть представлена объектом типа, `fpos_t`который хранит смещение и любую информацию состояния, необходимую для разбора широкого потока. Смещение ноль относится к первому элементу потока. (Объект типа [`pos_type`](../standard-library/basic-streambuf-class.md#pos_type) хранит хотя `fpos_t` бы объект.)

Для файла, открытого для чтения и записи, входной и выходной потоки располагаются вместе. Чтобы переключаться между вставкой и [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos)извлечением, необходимо позвонить либо или . Звонки `pubseekoff` (и, `seekoff`следовательно, ) имеют различные ограничения для [текстовых потоков,](../c-runtime-library/text-and-binary-streams.md) [двоичных потоков](../c-runtime-library/text-and-binary-streams.md)и [широких потоков.](../c-runtime-library/byte-and-wide-streams.md)

Если указатель `fp` файла является указателем null, функция выходит из строя. В противном случае он пытается изменить `fseek(fp, _Off, _Way)`положение потока, позвонив. Если эта функция удаётся, и полученная позиция `fposn` может быть определена путем вызова, `fgetpos(fp, &fposn)`функция преуспевает. Если функция успешно, она возвращает значение `pos_type` `fposn`типа, содержащего. В противном случае она возвращает недопустимую позицию потока.

## <a name="basic_filebufseekpos"></a><a name="seekpos"></a>basic_filebuf::seekpos

Пытается изменить текущие положения для управляемых потоков.

```cpp
virtual pos_type seekpos(
    pos_type _Sp,
    ios_base::openmode _Which = ios_base::in | ios_base::out);
```

### <a name="parameters"></a>Параметры

*_Sp*\
Позиция для поиска.

*_which*\
Задает режим для положения указателя. По умолчанию разрешается изменять позиции чтения и записи.

### <a name="return-value"></a>Возвращаемое значение

Если указатель `fp` файла является указателем null, функция выходит из строя. В противном случае он пытается изменить `fsetpos(fp, &fposn)`положение `fposn` потока, позвонив, где находится `fpos_t` объект, хранящийся в. `pos` Если эта функция выполняется успешно, функция возвращает `pos`. В противном случае она возвращает недопустимую позицию потока. Чтобы определить, является ли позиция в потоке недопустимой, сравните возвращаемое значение с `pos_type(off_type(-1))`.

### <a name="remarks"></a>Remarks

Защищенная функция виртуального члена пытается изменить текущие позиции для контролируемых потоков. Для объекта класса [`basic_filebuf`](../standard-library/basic-filebuf-class.md) `<Char_T, Tr>`позиция потока может быть представлена объектом типа, `fpos_t`который хранит смещение и любую информацию состояния, необходимую для разбора широкого потока. Смещение ноль относится к первому элементу потока. (Объект типа `pos_type` хранит по крайней мере объект `fpos_t`.)

Для файла, открытого для чтения и записи, входной и выходной потоки располагаются вместе. Чтобы переключаться между вставкой и [`pubseekoff`](../standard-library/basic-streambuf-class.md#pubseekoff) [`pubseekpos`](../standard-library/basic-streambuf-class.md#pubseekpos)извлечением, необходимо позвонить либо или . Звонки `pubseekoff` (и `seekoff`к ) имеют различные ограничения для потоков текста, бинарных потоков и широких потоков.

Что касается широкого потока, если после открытия такого потока или с момента последнего вызова `streampos` были произведены какие-либо вставки, то эта функция вызывает [переполнение](#overflow). Он также вставляет любую последовательность, необходимую для восстановления `fac` исходного состояния преобразования, используя грань преобразования файла для вызова `fac.unshift` по мере необходимости. Каждый `byte` произведенный элемент **символа** типа пишется в связанный поток, обозначенный `fp` `fputc(byte, fp)`указателем файла, как будто последовательными вызовами формы. Если вызов `fac.unshift` или любой записи не удается, функция не удается.

## <a name="basic_filebufsetbuf"></a><a name="setbuf"></a>basic_filebuf::setbuf

Выполняет операции, относящиеся непосредственно к каждому производному буферу потока.

```cpp
virtual basic_streambuf<Char_T, Tr> *setbuf(
    char_type* _Buffer,
    streamsize count);
```

### <a name="parameters"></a>Параметры

*_Buffer*\
Указатель на буфер.

*Рассчитывать*\
Размер буфера.

### <a name="return-value"></a>Возвращаемое значение

Эта защищенная функция-член возвращает нуль, если указатель файла `fp` является пустым указателем.

### <a name="remarks"></a>Remarks

`setbuf`вызовы, `setvbuf( fp, (char*) _Buffer, _IOFBF, count * sizeof( Char_T))` чтобы `count` предложить массив элементов, начиная с *_Buffer* в качестве буфера для потока. Если эта функция возвращает ненулевое значение, то возвращается пустой указатель. В противном случае она возвращает **this**, чтобы сообщить об успешном завершении.

## <a name="basic_filebufswap"></a><a name="swap"></a>basic_filebuf::swap

Меняет местами содержимое этого объекта `basic_filebuf` с содержимым указанного объекта `basic_filebuf`.

```cpp
void swap(basic_filebuf& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Ссылка на lvalue к другому `basic_filebuf`.

## <a name="basic_filebufsync"></a><a name="sync"></a>basic_filebuf::sync

Пытается синхронизировать управляемые потоки с любыми связанными внешними потоками.

```cpp
virtual int sync();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает ноль, если `fp` указатель файла является указателем null. В противном случае он возвращаетнулся `fflush(fp)` ноль только в том случае, если вызовы как [переполнения,](#overflow) так и успех в промывке любого ожидающего вывода в поток.

## <a name="basic_filebuftraits_type"></a><a name="traits_type"></a>basic_filebuf::traits_type

Связывает имя типа с параметром шаблона `Tr`.

```cpp
typedef Tr traits_type;
```

## <a name="basic_filebufunderflow"></a><a name="underflow"></a>basic_filebuf::underflow

Извлекает текущий элемент из входного потока.

```cpp
virtual int_type underflow();
```

### <a name="return-value"></a>Возвращаемое значение

Если функция не может быть `traits_type::` [`eof`](../standard-library/char-traits-struct.md#eof)успешной, она возвращается. В противном `ch`случае, он возвращается, преобразуется, как описано в разделе Замечания.

### <a name="remarks"></a>Remarks

Защищенная функция виртуального члена пытается `ch` извлечь текущий элемент из входного потока и вернуть элемент как. `traits_type::` [`to_int_type`](../standard-library/char-traits-struct.md#to_int_type) `(ch)` Это можно сделать разными способами.

- Если позиция чтения доступна, `ch` она принимает элемент, хранящийся в положении чтения, и продвигает следующий указатель для буфера ввода.

- Он может читать один или **char**несколько элементов типа char `fgetc(fp)`, как будто `ch` последовательными вызовами формы, и преобразовать их в элемент типа `Char_T` с помощью аспекта преобразования файла `fac` для вызова `fac.in` по мере необходимости. В случае сбоя какого-либо преобразования или операции чтения эта функция завершается неудачно.

## <a name="see-also"></a>См. также раздел

[\<>fstream](../standard-library/fstream.md)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[программирование йострима](../standard-library/iostream-programming.md)\
[iostreams Конвенций](../standard-library/iostreams-conventions.md)
