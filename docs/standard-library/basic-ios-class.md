---
title: Класс basic_ios | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- ios/std::basic_ios
- ios/std::basic_ios::char_type
- ios/std::basic_ios::int_type
- ios/std::basic_ios::off_type
- ios/std::basic_ios::pos_type
- ios/std::basic_ios::traits_type
- ios/std::basic_ios::bad
- ios/std::basic_ios::clear
- ios/std::basic_ios::copyfmt
- ios/std::basic_ios::eof
- ios/std::basic_ios::exceptions
- ios/std::basic_ios::fail
- ios/std::basic_ios::fill
- ios/std::basic_ios::good
- ios/std::basic_ios::imbue
- ios/std::basic_ios::init
- ios/std::basic_ios::move
- ios/std::basic_ios::narrow
- ios/std::basic_ios::rdbuf
- ios/std::basic_ios::rdstate
- ios/std::basic_ios::set_rdbuf
- ios/std::basic_ios::setstate
- ios/std::basic_ios::swap
- ios/std::basic_ios::tie
- ios/std::basic_ios::widen
- ios/std::basic_ios::explicit operator bool
dev_langs:
- C++
helpviewer_keywords:
- std::basic_ios [C++]
- std::basic_ios [C++], char_type
- std::basic_ios [C++], int_type
- std::basic_ios [C++], off_type
- std::basic_ios [C++], pos_type
- std::basic_ios [C++], traits_type
- std::basic_ios [C++], bad
- std::basic_ios [C++], clear
- std::basic_ios [C++], copyfmt
- std::basic_ios [C++], eof
- std::basic_ios [C++], exceptions
- std::basic_ios [C++], fail
- std::basic_ios [C++], fill
- std::basic_ios [C++], good
- std::basic_ios [C++], imbue
- std::basic_ios [C++], init
- std::basic_ios [C++], move
- std::basic_ios [C++], narrow
- std::basic_ios [C++], rdbuf
- std::basic_ios [C++], rdstate
- std::basic_ios [C++], set_rdbuf
- std::basic_ios [C++], setstate
- std::basic_ios [C++], swap
- std::basic_ios [C++], tie
- std::basic_ios [C++], widen
ms.assetid: 4fdcd8e1-62d2-4611-8a70-1e4f58434007
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28854866824b1750fb1887d5e822d2165034f687
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956847"
---
# <a name="basicios-class"></a>Класс basic_ios

Этот класс шаблона описывает хранилище и функции-члены, общие для входных потоков (класс шаблона [basic_istream](../standard-library/basic-istream-class.md)) и выходных потоков (класс шаблона [basic_ostream](../standard-library/basic-ostream-class.md)), которые зависят от параметров шаблона. (Класс [basic_ios](../standard-library/ios-base-class.md) описывает общие принципы, не зависящие от параметров шаблона.) Объект класса **basic_ios\<class Elem, class Traits >** помогает управлять потоком с элементами типа `Elem`, признаки символов определяются классом `Traits`.

## <a name="syntax"></a>Синтаксис

```cpp

template <class Elem, class Traits>
class basic_ios : public ios_base
```

### <a name="parameters"></a>Параметры

*Elem* типом.

*Признаки* переменной типа `char_traits`.

## <a name="remarks"></a>Примечания

Объект класса **basic_ios\<class Elem, class Traits>** хранит следующее.

- Указатель на объект типа [basic_istream](../standard-library/basic-istream-class.md)**\<Elem, Traits>**.

- Указатель буфера потока на объект типа [basic_streambuf](../standard-library/basic-streambuf-class.md)**\<Elem, Traits >**.

- [Сведения о форматировании](../standard-library/ios-base-class.md).

- [Сведения о состоянии потока](../standard-library/ios-base-class.md) в базовом объекте типа [ios_base](../standard-library/ios-base-class.md).

- Символ заполнения в объекте типа `char_type`.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание:|
|-|-|
|[basic_ios](#basic_ios)|Создает класс `basic_ios`.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание:|
|-|-|
|[char_type](#char_type)|Синоним параметра шаблона `Elem`.|
|[int_type](#int_type)|Синоним для `Traits::int_type`.|
|[off_type](#off_type)|Синоним для `Traits::off_type`.|
|[pos_type](#pos_type)|Синоним для `Traits::pos_type`.|
|[traits_type](#traits_type)|Синоним параметра шаблона `Traits`.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание:|
|-|-|
|[bad](#bad)|Сообщает о потере целостности буфера потока.|
|[clear](#clear)|Очищает все флаги ошибок.|
|[copyfmt](#copyfmt)|Копирует флаги из одного потока в другой.|
|[eof](#eof)|Указывает, достигнут ли конец потока.|
|[exceptions](#exceptions)|Указывает, какие исключения будут создаваться потоком.|
|[fail](#fail)|Сообщает об ошибке при извлечении допустимого поля из потока.|
|[fill](#fill)|Задает или возвращает символ, который будет использоваться, если ширина текста не совпадает с шириной потока.|
|[good](#good)|Указывает, что поток находится в хорошем состоянии.|
|[imbue](#imbue)|Изменяет языковой стандарт.|
|[init](#init)|Вызывается конструкторами `basic_ios`.|
|[move](#move)|Перемещает все значения, кроме указателя на буфер потока, из параметра в текущий объект.|
|[narrow](#narrow)|Находит эквивалентный char для данного `char_type`.|
|[rdbuf](#rdbuf)|Направляет поток в указанный буфер.|
|[rdstate](#rdstate)|Считывает состояние битов для флагов.|
|[set_rdbuf](#set_rdbuf)|Назначает буфер потока буфером чтения для этого объекта потока.|
|[setstate](#setstate)|Устанавливает дополнительные флаги.|
|[swap](#swap)|Меняет местами значения в этом объекте `basic_ios` и значения другого объекта `basic_ios`. Указатели на буферы потока не меняются местами.|
|[tie](#tie)|Гарантирует, что один поток обрабатывается до другого потока.|
|[widen](#widen)|Находит эквивалент `char_type` для указанного char.|

### <a name="operators"></a>Операторы

|Оператор|Описание:|
|-|-|
|[explicit operator bool](#op_bool)|Позволяет использовать `basic_ios` объекта в виде **bool**. Автоматическое преобразование типов отключено для предотвращения распространенных непредвиденных побочных эффектов.|
|[operator void *](#op_void_star)|Указывает, находится ли поток по-прежнему в хорошем состоянии.|
|[оператор!](#op_not)|Указывает, не находится ли поток в плохом состоянии.|

## <a name="requirements"></a>Требования

**Заголовок:** \<ios>

**Пространство имен:** std

## <a name="bad"></a>  basic_ios::bad

Сообщает о потере целостности буфера потока.

```cpp
bool bad() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если `rdstate & badbit` ненулевое значение; в противном случае **false**.

Дополнительные сведения по `badbit` см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

### <a name="example"></a>Пример

```cpp
// basic_ios_bad.cpp
// compile with: /EHsc
#include <iostream>

int main( void )
{
    using namespace std;
    bool b = cout.bad( );
    cout << boolalpha;
    cout << b << endl;

    b = cout.good( );
    cout << b << endl;
}
```

## <a name="basic_ios"></a>  basic_ios::basic_ios

Конструирует класс basic_ios.

```cpp
explicit basic_ios(basic_streambuf<Elem,  Traits>* sb);
basic_ios();
```

### <a name="parameters"></a>Параметры

*SB* стандартный буфер для хранения элементов ввода или вывода.

### <a name="remarks"></a>Примечания

Первый конструктор инициализирует свой объект-член путем вызова [init](#init)(_ *Sb*). Второй (защищенный) конструктор оставляет свои объекты-члены не инициализированными. Последующий вызов `init` должен инициализировать объект, прежде чем он может быть безопасно уничтожен.

## <a name="char_type"></a>  basic_ios::char_type

Синоним параметра шаблона `Elem`.

```cpp
typedef Elem char_type;
```

## <a name="clear"></a>  basic_ios::clear

Очищает все флаги ошибок.

```cpp
void clear(iostate state = goodbit, bool reraise = false);
void clear(io_state state);
```

### <a name="parameters"></a>Параметры

*состояние* (необязательно) флаги нужно задать после очистки всех флагов. По умолчанию — `goodbit`.

*reraise-* (необязательный) определяет ли исключение должно быть заново создать исключение. По умолчанию используется **false** (не будет создано заново исключение).

### <a name="remarks"></a>Примечания

Флаги — `goodbit`, `failbit`, `eofbit`, и `badbit`. Проверяет наличие этих флагов с помощью [good](#good), [bad](#bad), [eof](#eof) и [fail](#fail)

Функция-член заменяет сохраненную информацию о состоянии потока на следующее:

`state` &#124; `(`[rdbuf](#rdbuf) != 0 **goodbit** : **badbit**)

Если `state`**&**[exceptions](#exceptions) имеет ненулевое значение, то создается объект класса [failure](../standard-library/ios-base-class.md#failure).

### <a name="example"></a>Пример

См. в разделе [rdstate](#rdstate) и [getline](../standard-library/string-functions.md#getline) примеры использования `clear`.

## <a name="copyfmt"></a>  basic_ios::copyfmt

Копирует флаги из одного потока в другой.

```cpp
basic_ios<Elem, Traits>& copyfmt(
const basic_ios<Elem, Traits>& right);
```

### <a name="parameters"></a>Параметры

*правом* поток, флаги которого требуется скопировать.

### <a name="return-value"></a>Возвращаемое значение

Объект **this** для потока, в который копируются флаги.

### <a name="remarks"></a>Примечания

Функция-член сообщает событие обратного вызова **стереть\_событий**. Затем она копирует из *правой* в  **\*это** символ заливки, указатель tie и сведения о форматировании. Перед изменением маски исключения, он сообщает событие обратного вызова `copyfmt_event`. Если после завершения копирования **state &** [exceptions](#exceptions) не равно нулю, функция эффективно вызывает [clear](#clear) с аргументом [rdstate](#rdstate). Она возвращает **\*this**.

### <a name="example"></a>Пример

```cpp
// basic_ios_copyfmt.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

int main( )
{
    using namespace std;
    ofstream x( "test.txt" );
    int i = 10;

    x << showpos;
    cout << i << endl;
    cout.copyfmt( x );
    cout << i << endl;
}

```

## <a name="eof"></a>  basic_ios::eof

Указывает, достигнут ли конец потока.

```cpp
bool eof() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если был достигнут конец потока, **false** в противном случае.

### <a name="remarks"></a>Примечания

Функция-член возвращает **true** Если [rdstate](#rdstate) `& eofbit` имеет ненулевое значение. Дополнительные сведения по `eofbit` см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

### <a name="example"></a>Пример

```cpp
// basic_ios_eof.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>

using namespace std;

int main( int argc, char* argv[] )
{
    fstream   fs;
    int n = 1;
    fs.open( "basic_ios_eof.txt" );   // an empty file
    cout << boolalpha
    cout << fs.eof() << endl;
    fs >> n;   // Read the char in the file
    cout << fs.eof() << endl;
}
```

## <a name="exceptions"></a>  basic_ios::exceptions

Указывает, какие исключения будут создаваться потоком.

```cpp
iostate exceptions() const;
void exceptions(iostate Newexcept);
void exceptions(io_state Newexcept);
```

### <a name="parameters"></a>Параметры

*Newexcept* флаги, которые должны вызывать исключение.

### <a name="return-value"></a>Возвращаемое значение

Флаги, указанные в настоящий момент для создания исключения для потока.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает сохраненную маску исключения. Вторая функция-член сохраняет *_Except* в маске исключения и возвращает предыдущее хранившееся там значение. Обратите внимание, что сохранение новой маски исключения может вызвать исключение так же, как вызов [clear](#clear)( [rdstate](#rdstate) ).

### <a name="example"></a>Пример

```cpp
// basic_ios_exceptions.cpp
// compile with: /EHsc /GR
#include <iostream>

int main( )
{
    using namespace std;

    cout << cout.exceptions( ) << endl;
    cout.exceptions( ios::eofbit );
    cout << cout.exceptions( ) << endl;
    try
    {
        cout.clear( ios::eofbit );   // Force eofbit on
    }
    catch ( exception &e )
    {
        cout.clear( );
        cout << "Caught the exception." << endl;
        cout << "Exception class: " << typeid(e).name()  << endl;
        cout << "Exception description: " << e.what() << endl;
    }
}
```

```Output
0
1
Caught the exception.
Exception class: class std::ios_base::failure
Exception description: ios_base::eofbit set
```

## <a name="fail"></a>  basic_ios::fail

Сообщает об ошибке при извлечении допустимого поля из потока.

```cpp
bool fail() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если [rdstate](#rdstate) `& (badbit|failbit)` не равно нулю, в противном случае **false**.

Дополнительные сведения по `failbit` см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

### <a name="example"></a>Пример

```cpp
// basic_ios_fail.cpp
// compile with: /EHsc
#include <iostream>

int main( void )
{
    using namespace std;
    bool b = cout.fail( );
    cout << boolalpha;
    cout << b << endl;
}

```

## <a name="fill"></a>  basic_ios::fill

Задает или возвращает символ, который будет использоваться, если ширина текста не совпадает с шириной потока.

```cpp
char_type fill() const;
char_type fill(char_type Char);
```

### <a name="parameters"></a>Параметры

*Char* знаком в качестве символа заливки.

### <a name="return-value"></a>Возвращаемое значение

Текущий символ заливки.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает сохраненный символ заливки. Вторая функция-член сохраняет *Char* в символе заливки и возвращает его ранее сохраненное значение.

### <a name="example"></a>Пример

```cpp
// basic_ios_fill.cpp
// compile with: /EHsc
#include <iostream>
#include <iomanip>

int main( )
{
    using namespace std;

    cout << setw( 5 ) << 'a' << endl;
    cout.fill( 'x' );
    cout << setw( 5 ) << 'a' << endl;
    cout << cout.fill( ) << endl;
}
```

```Output
a
xxxxa
x
```

## <a name="good"></a>  basic_ios::good

Указывает, что поток находится в хорошем состоянии.

```cpp
bool good() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если [rdstate](#rdstate) `== goodbit` (флаги состояния не установлены), в противном случае **false**.

Дополнительные сведения по `goodbit` см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

### <a name="example"></a>Пример

Пример использования `good` разделе [basic_ios::bad](#bad).

## <a name="imbue"></a>  basic_ios::imbue

Изменяет языковой стандарт.

```cpp
locale imbue(const locale& Loc);
```

### <a name="parameters"></a>Параметры

*Loc* строка языкового стандарта.

### <a name="return-value"></a>Возвращаемое значение

Предыдущий языковой стандарт.

### <a name="remarks"></a>Примечания

Если [rdbuf](#rdbuf) не является пустым указателем, функция-член вызывает

`rdbuf`-> [pubimbue](../standard-library/basic-streambuf-class.md#pubimbue)(_ *Loc*)

В любом случае возвращается [ios_base::imbue](../standard-library/ios-base-class.md#imbue)(_ *Loc*).

### <a name="example"></a>Пример

```cpp
// basic_ios_imbue.cpp
// compile with: /EHsc
#include <iostream>
#include <locale>

int main( )
{
    using namespace std;

    cout.imbue( locale( "french_france" ) );
    double x = 1234567.123456;
    cout << x << endl;
}
```

## <a name="init"></a>  basic_ios::init

Вызывается конструкторами basic_ios.

```cpp
void init(basic_streambuf<Elem,Traits>* _Sb, bool _Isstd = false);
```

### <a name="parameters"></a>Параметры

*_Sb* стандартный буфер для хранения элементов ввода или вывода.

*_Isstd* указывает, является ли это стандартный поток.

### <a name="remarks"></a>Примечания

Функция-член сохраняет значения во всех объектах-членах, так что:

- [rdbuf](#rdbuf) возвращает *_Sb*;

- [tie](#tie) возвращает пустой указатель;

- [rdstate](#rdstate) возвращает [goodbit](../standard-library/ios-base-class.md#iostate) Если *_Sb* равен нулю; в противном случае — значение возвращается [badbit](../standard-library/ios-base-class.md#iostate).

- [исключения](#exceptions) возвращает `goodbit`.

- [flags](../standard-library/ios-base-class.md#flags) возвращает [skipws](../standard-library/ios-base-class.md#fmtflags) &#124; [dec](../standard-library/ios-base-class.md#fmtflags);

- [width](../standard-library/ios-base-class.md#width) возвращает 0;

- [precision](../standard-library/ios-base-class.md#precision) возвращает 6;

- [fill](#fill) возвращает символ пробела;

- [getloc](../standard-library/ios-base-class.md#getloc) возвращает `locale::classic`;

- [iword](../standard-library/ios-base-class.md#iword) возвращает ноль, и [pword](../standard-library/ios-base-class.md#pword) возвращает пустой указатель для всех значений аргумента.

## <a name="int_type"></a>  basic_ios::int_type

Синоним для `traits_type::int_type`.

```cpp
typedef typename traits_type::int_type int_type;
```

## <a name="move"></a>  basic_ios::move

Перемещает все значения, кроме указателя на буфер потока, из параметра в текущий объект.

```cpp
void move(basic_ios&& right);
```

### <a name="parameters"></a>Параметры

*правом* `ios_base` объект для перемещения значений.

### <a name="remarks"></a>Примечания

Защищенная функция-член перемещает все значения, хранящиеся в *правой* для `*this` за исключением сохраненного `stream buffer pointer`, который не изменяется в *правой* и присваивается пустой указатель в `*this`. Сохраненный `tie pointer` присваивается пустой указатель в *правой*.

## <a name="narrow"></a>  basic_ios::narrow

Находит эквивалентный char для данного `char_type`.

```cpp
char narrow(char_type Char, char Default = '\0') const;
```

### <a name="parameters"></a>Параметры

*Char* **char** для преобразования.

*По умолчанию* **char** который должен возвращаться, если эквивалент не будет найден.

### <a name="return-value"></a>Возвращаемое значение

Эквивалент **char** для заданного `char_type`.

### <a name="remarks"></a>Примечания

Функция-член возвращает [use_facet](../standard-library/basic-filebuf-class.md#open)\<ctype\<E >> ( [getloc](../standard-library/ios-base-class.md#getloc)()).`narrow` ( `Char`, `Default`).

### <a name="example"></a>Пример

```cpp
// basic_ios_narrow.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <wchar.h>

int main( )
{
    using namespace std;
    wchar_t *x = L"test";
    char y[10];
    cout << x[0] << endl;
    wcout << x << endl;
    y[0] = wcout.narrow( x[0] );
    cout << y[0] << endl;
}
```

## <a name="off_type"></a>  basic_ios::off_type

Синоним для `traits_type::off_type`.

```cpp
typedef typename traits_type::off_type off_type;
```

## <a name="op_void_star"></a>  basic_ios::operator void *

Указывает, находится ли поток по-прежнему в хорошем состоянии.

```cpp
operator void *() const;
```

### <a name="return-value"></a>Возвращаемое значение

Оператор возвращает пустой указатель только в том случае, если [fail](#fail).

### <a name="example"></a>Пример

```cpp
// basic_ios_opgood.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    cout << (bool)(&cout != 0) << endl;   // Stream is still good
}
```

```Output
1
```

## <a name="op_not"></a>  basic_ios::operator!

Указывает, не находится ли поток в плохом состоянии.

```cpp
bool operator!() const;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает [fail](#fail).

### <a name="example"></a>Пример

```cpp
// basic_ios_opbad.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
    using namespace std;
    cout << !cout << endl;   // Stream is not bad
}
```

```Output
0
```

## <a name="op_bool"></a>  basic_ios::operator bool

Позволяет использовать `basic_ios` объекта в виде **bool**. Автоматическое преобразование типов отключено для предотвращения распространенных непредвиденных побочных эффектов.

```cpp
explicit operator bool() const;
```

### <a name="remarks"></a>Примечания

Оператор возвращает значение, преобразуемое в **false** только если `fail()`. Тип возвращаемого значения можно преобразовать только в **bool**, а не в `void *` или другие известные скалярные типы.

## <a name="pos_type"></a>  basic_ios::pos_type

Синоним для `traits_type::pos_type`.

```cpp
typedef typename traits_type::pos_type pos_type;
```

## <a name="rdbuf"></a>  basic_ios::rdbuf

Направляет поток в указанный буфер.

```cpp
basic_streambuf<Elem, Traits> *rdbuf() const;
basic_streambuf<Elem, Traits> *rdbuf(
basic_streambuf<Elem, Traits>* _Sb);
```

### <a name="parameters"></a>Параметры

*_Sb* потока.

### <a name="remarks"></a>Примечания

Первая функция-член возвращает сохраненный указатель буфера потока.

Вторая функция-член сохраняет *_Sb* в сохраненном указателе буфера потока и возвращает ранее сохраненное значение.

### <a name="example"></a>Пример

```cpp
// basic_ios_rdbuf.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <fstream>

int main( )
{
    using namespace std;
    ofstream file( "rdbuf.txt" );
    streambuf *x = cout.rdbuf( file.rdbuf( ) );
    cout << "test" << endl;   // Goes to file
    cout.rdbuf(x);
    cout << "test2" << endl;
}
```

```Output
test2
```

## <a name="rdstate"></a>  basic_ios::rdstate

Считывает состояние битов для флагов.

```cpp
iostate rdstate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Сведения о состоянии сохраненного потока.

### <a name="example"></a>Пример

```cpp
// basic_ios_rdstate.cpp
// compile with: /EHsc
#include <iostream>
#include <fstream>
using namespace std;

void TestFlags( ios& x )
{
    cout << ( x.rdstate( ) & ios::badbit ) << endl;
    cout << ( x.rdstate( ) & ios::failbit ) << endl;
    cout << ( x.rdstate( ) & ios::eofbit ) << endl;
    cout << endl;
}

int main( )
{
    fstream x( "c:\test.txt", ios::out );
    x.clear( );
    TestFlags( x );
    x.clear( ios::badbit | ios::failbit | ios::eofbit );
    TestFlags( x );
}
```

```Output
0
0
0

4
2
1
```

## <a name="setstate"></a>  basic_ios::setstate

Устанавливает дополнительные флаги.

```cpp
void setstate(iostate _State);
```

### <a name="parameters"></a>Параметры

*_State* дополнительные флаги для установки.

### <a name="remarks"></a>Примечания

Эта функция-член эффективно вызывает [clear](#clear)(_ *State* &#124; [rdstate](#rdstate)).

### <a name="example"></a>Пример

```cpp
// basic_ios_setstate.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
using namespace std;

int main( )
{
    bool b = cout.bad( );
    cout << b << endl;   // Good
    cout.clear( ios::badbit );
    b = cout.bad( );
    // cout.clear( );
    cout << b << endl;   // Is bad, good
    b = cout.fail( );
    cout << b << endl;   // Not failed
    cout.setstate( ios::failbit );
    b = cout.fail( );
    cout.clear( );
    cout << b << endl;   // Is failed, good
    return 0;
}
```

```Output
0
1
```

## <a name="set_rdbuf"></a>  basic_ios::set_rdbuf

Назначает буфер потока буфером чтения для этого объекта потока.

```cpp
void set_rdbuf(
basic_streambuf<Elem, Tr>* strbuf)
```

### <a name="parameters"></a>Параметры

*strbuf* буфер потока, чтобы стать буфером чтения.

### <a name="remarks"></a>Примечания

Функция сохраняет защищенный член *strbuf* в `stream buffer pointer`. Он не вызывает `clear`.

## <a name="tie"></a>  basic_ios::tie

Гарантирует, что один поток обрабатывается до другого потока.

```cpp
basic_ostream<Elem, Traits> *tie() const;
basic_ostream<Elem, Traits> *tie(
basic_ostream<Elem, Traits>* str);
```

### <a name="parameters"></a>Параметры

*STR* потока.

### <a name="return-value"></a>Возвращаемое значение

Первая функция-член возвращает сохраненный указатель tie. Вторая функция-член сохраняет *str* в указателе tie и возвращает его ранее сохраненное значение.

### <a name="remarks"></a>Примечания

`tie` вызывает синхронизацию двух потоков, так что операции в одном потоке операций происходят после завершения операций в другом потоке.

### <a name="example"></a>Пример

В этом примере путем связывания cin с cout гарантируется, что строка "Enter a number:" будет появляться на консоли перед самим номером, извлекаемым из cin. Это исключает возможность того, что строка "Enter a number:" будет оставаться в буфере при считывании номера, и таким образом мы гарантируем, что пользователь фактически получает некоторый запрос, на который нужно отреагировать. По умолчанию cin и cout связаны.

```cpp
#include <ios>
#include <iostream>

int main( )
{
    using namespace std;
    int i;
    cin.tie( &cout );
    cout << "Enter a number:";
    cin >> i;
}
```

## <a name="traits_type"></a>  basic_ios::traits_type

Синоним параметра шаблона `Traits`.

```cpp
typedef Traits traits_type;
```

## <a name="widen"></a>  basic_ios::widen

Находит эквивалент `char_type` для заданного **char**.

```cpp
char_type widen(char Char) const;
```

### <a name="parameters"></a>Параметры

*Char* знак для преобразования.

### <a name="return-value"></a>Возвращаемое значение

Находит эквивалент `char_type` для заданного **char**.

### <a name="remarks"></a>Примечания

Функция-член возвращает [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype**\< **E**> >( [getloc](../standard-library/ios-base-class.md#getloc)). `widen`( `Char`).

### <a name="example"></a>Пример

```cpp
// basic_ios_widen.cpp
// compile with: /EHsc
#include <ios>
#include <iostream>
#include <wchar.h>

int main( )
{
    using namespace std;
    char *z = "Hello";
    wchar_t y[2] = {0,0};
    cout << z[0] << endl;
    y[0] = wcout.widen( z[0] );
    wcout << &y[0] << endl;
}

```

## <a name="swap"></a>  basic_ios::swap

Меняет местами значения в этом объекте `basic_ios` и значения другого объекта `basic_ios`. Однако указатели на буферы потока не меняются местами.

```cpp
void swap(basic_ios&& right);
```

### <a name="parameters"></a>Параметры

*правом* `basic_ios` объект, используемый для обмена значений.

### <a name="remarks"></a>Примечания

Защищенная функция-член меняет местами все значения, хранящиеся в *правой* с `*this` за исключением сохраненного `stream buffer pointer`.

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[Программирование iostream](../standard-library/iostream-programming.md)<br/>
[Соглашения iostreams](../standard-library/iostreams-conventions.md)<br/>
