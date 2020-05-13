---
title: Функции &lt;string&gt;
ms.date: 11/04/2016
f1_keywords:
- string/std::getline
- string/std::stod
- string/std::stof
- string/std::stoi
- string/std::stol
- string/std::stold
- string/std::stoll
- string/std::stoul
- string/std::stoull
- string/std::swap
- string/std::to_string
- string/std::to_wstring
ms.assetid: 1a4ffd11-dce5-4cc6-a043-b95de034c7c4
helpviewer_keywords:
- std::getline [C++]
- std::stod [C++]
- std::stof [C++]
- std::stoi [C++]
- std::stol [C++]
- std::stold [C++]
- std::stoll [C++]
- std::stoul [C++]
- std::stoull [C++]
- std::swap [C++]
- std::to_string [C++]
- std::to_wstring [C++]
ms.openlocfilehash: 3f1dca71a6bb9d5461150378191b9373f907ecd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376663"
---
# <a name="ltstringgt-functions"></a>Функции &lt;string&gt;

||||
|-|-|-|
|[getline](#getline)|[stod](#stod)|[стус](#stof)|
|[стои](#stoi)|[stol](#stol)|[stold](#stold)|
|[stoll](#stoll)|[stoul](#stoul)|[stoull](#stoull)|
|[Своп](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|

## <a name="getline"></a><a name="getline"></a>получить линию

Извлекает строки из входного потока, последовательно по одной строке.

```cpp
// (1) delimiter as parameter
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& in_stream,
    basic_string<CharType, Traits, Allocator>& str,
    CharType delimiter);

template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>&& in_stream,
    basic_string<CharType, Traits, Allocator>& str,
    const CharType delimiter);

// (2) default delimiter used
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& in_stream,
    basic_string<CharType, Traits, Allocator>& str);

template <class Allocator, class Traits, class Allocator>
basic_istream<Allocator, Traits>& getline(
    basic_istream<Allocator, Traits>&& in_stream,
    basic_string<Allocator, Traits, Allocator>& str);
```

### <a name="parameters"></a>Параметры

*in_stream*\
Входной поток, из которого извлекается строка.

*Ул*\
Строка, в которую считываются символы из входного потока.

*Разделитель*\
Разделитель строк.

### <a name="return-value"></a>Возвращаемое значение

Вхотогий поток *in_stream*.

### <a name="remarks"></a>Remarks

Пара сигнатур `(1)` функций с пометкой экстракт символов из *in_stream* до тех пор, пока *делимитер* не будет найден, храним их в *str.*

Пара отмеченных `(2)` подписей функций использует newline в качестве `getline(in_stream, str, in_stream. widen('\n'))`делимитера линии по умолчанию и ведет себя как.

Вторая функция каждой пары аналогична первой и поддерживает [ссылки rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md).

Извлечение останавливается при возникновении одного из следующих условий.

- В конце файла, и в этом случае внутренний государственный флаг *in_stream* установлен на `ios_base::eofbit`.

- После функции извлекает элемент, который сравнивается с *делимитетом.* Элемент не возвращается или не пригоздале к контролируемой последовательности.

- После функции `str.`извлекает [max_size](../standard-library/basic-string-class.md#max_size) элементы. Внутренний государственный *in_stream* флаг in_stream `ios_base::failbit`установлен на .

- Некоторые другие ошибки, кроме ранее перечисленных; внутренний государственный *in_stream* флаг in_stream `ios_base::badbit`установлен на .

Сведения о внутренних флагах состояния см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

Если функция не извлекает элементов, *in_stream* внутренний флаг `ios_base::failbit`состояния in_stream установлен. В любом `getline` случае, *возвращается in_stream*.

Если исключение брошено, *in_stream* и *str* остаются в допустимом состоянии.

### <a name="example"></a>Пример

Следующий код демонстрирует `getline()` в двух режимах: в первом с разделителем — символом новой строки (по умолчанию), во втором с разделителем — пробелом. Символ конца файла (CTRL-Z на клавиатуре) используется для управления завершением циклов while. Это значение устанавливает внутренний `cin` `eofbit`флаг состояния к, который должен быть очищен с [basic_ios::ясным()](../standard-library/basic-ios-class.md#clear) до второго, в то время как цикл будет работать должным образом.

```cpp
// compile with: /EHsc /W4
#include <string>
#include <iostream>
#include <vector>

using namespace std;

int main()
{
    string str;
    vector<string> v1;
    cout << "Enter a sentence, press ENTER between sentences. (Ctrl-Z to stop): " << endl;
    // Loop until end-of-file (Ctrl-Z) is input, store each sentence in a vector.
    // Default delimiter is the newline character.
    while (getline(cin, str)) {
        v1.push_back(str);
    }

    cout << "The following input was stored with newline delimiter:" << endl;
    for (const auto& p : v1) {
        cout << p << endl;
    }

    cin.clear();

    vector<string> v2;
    // Now try it with a whitespace delimiter
    while (getline(cin, str, ' ')) {
        v2.push_back(str);
    }

    cout << "The following input was stored with whitespace as delimiter:" << endl;
    for (const auto& p : v2) {
        cout << p << endl;
    }
}
```

## <a name="stod"></a><a name="stod"></a>stod

Преобразует последовательность символов **`double`** в .

```cpp
double stod(
    const string& str,
    size_t* idx = 0);

double stod(
    const wstring& str,
    size_t* idx = 0
;
```

### <a name="parameters"></a>Параметры

*Ул*\
Последовательность символов для преобразования.

*Idx*\
Значение индекса первого непреобразованного символа.

### <a name="return-value"></a>Возвращаемое значение

Значение. **`double`**

### <a name="remarks"></a>Remarks

Функция преобразует последовательность элементов в *str* в **`double`** значение типа, как будто вызывая, `strtod( str.c_str(), _Eptr)`где `_Eptr` объект внутренний к функции. Если `str.c_str() == *_Eptr`он бросает объект типа. `invalid_argument` Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является `*_Eptr -  str.c_str()` `*idx` нулевой указатель, функция хранит и возвращает значение.

## <a name="stof"></a><a name="stof"></a>стус

Преобразует последовательность символов в число с плавающей запятой.

```cpp
float stof(
    const string& str,
    size_t* idx = 0);

float stof(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Параметры

*Ул*\
Последовательность символов для преобразования.

*Idx*\
Значение индекса первого непреобразованного символа.

### <a name="return-value"></a>Возвращаемое значение

Значение. **`float`**

### <a name="remarks"></a>Remarks

Функция преобразует последовательность элементов в *str* в **`float`** значение типа, как будто вызывая, `strtof( str.c_str(), _Eptr)`где `_Eptr` объект внутренний к функции. Если `str.c_str() == *_Eptr`он бросает объект типа. `invalid_argument` Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является `*_Eptr -  str.c_str()` `*idx` нулевой указатель, функция хранит и возвращает значение.

## <a name="stoi"></a><a name="stoi"></a>стои

Преобразует последовательность символов в целое число.

```cpp
int stoi(
    const string& str,
    size_t* idx = 0,
    int base = 10);

int stoi(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="return-value"></a>Возвращаемое значение

Целочисленное значение.

### <a name="parameters"></a>Параметры

*Ул*\
Последовательность символов для преобразования.

*Idx*\
Значение индекса первого непреобразованного символа.

*Базы*\
Используемое числовое основание.

### <a name="remarks"></a>Remarks

Функция `stoi` преобразует последовательность символов в *str* в **`int`** значение типа и возвращает значение. Например, если передать последовательность символов "10", `stoi` возвращает целочисленное значение 10.

`stoi`ведет себя аналогично функции `strtol` для однобайных символов, когда она `strtol( str.c_str(), _Eptr, idx)`называется таким образом, где `_Eptr` объект внутренний к функции; или `wcstol` для широких символов, когда это `wcstol(Str.c_str(), _Eptr, idx)`называется аналогичным образом, . Дополнительные сведения см. в разделе [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md).

`str.c_str() == *_Eptr`Если, `stoi` бросает объект типа `invalid_argument`. Если такой вызов `errno`будет установлен, или если возвращенное значение не **`int`** может быть представлено как `out_of_range`объект типа, он бросает объект типа. В противном случае, если *idx* не является `*_Eptr - str.c_str()` `*idx`нулевой указатель, функция хранится в .

## <a name="stol"></a><a name="stol"></a>Штол

Преобразует последовательность символов **`long`** в .

```cpp
long stol(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long stol(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Параметры

*Ул*\
Последовательность символов для преобразования.

*Idx*\
Значение индекса первого непреобразованного символа.

*Базы*\
Используемое числовое основание.

### <a name="return-value"></a>Возвращаемое значение

Длинное целое значение.

### <a name="remarks"></a>Remarks

Функция преобразует последовательность элементов в *str* в **`long`** значение типа, как будто вызывая, `strtol( str.c_str(), _Eptr, idx)`где `_Eptr` объект внутренний к функции. Если `str.c_str() == *_Eptr`он бросает объект типа. `invalid_argument` Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является `*_Eptr -  str.c_str()` `*idx` нулевой указатель, функция хранит и возвращает значение.

## <a name="stold"></a><a name="stold"></a>stold

Преобразует последовательность символов **`long double`** в .

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Параметры

*Ул*\
Последовательность символов для преобразования.

*Idx*\
Значение индекса первого непреобразованного символа.

### <a name="return-value"></a>Возвращаемое значение

Значение. **`long double`**

### <a name="remarks"></a>Remarks

Функция преобразует последовательность элементов в *str* в **`long double`** значение типа, как будто вызывая, `strtold( str.c_str(), _Eptr)`где `_Eptr` объект внутренний к функции. Если `str.c_str() == *_Eptr`он бросает объект типа. `invalid_argument` Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является `*_Eptr -  str.c_str()` `*idx` нулевой указатель, функция хранит и возвращает значение.

## <a name="stoll"></a><a name="stoll"></a>Stoll

Преобразует последовательность символов **`long long`** в .

```cpp
long long stoll(
    const string& str,
    size_t* idx = 0,
    int base = 10);

long long stoll(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Параметры

*Ул*\
Последовательность символов для преобразования.

*Idx*\
Значение индекса первого непреобразованного символа.

*Базы*\
Используемое числовое основание.

### <a name="return-value"></a>Возвращаемое значение

Значение. **`long long`**

### <a name="remarks"></a>Remarks

Функция преобразует последовательность элементов в *str* в **`long long`** значение типа, как будто вызывая, `strtoll( str.c_str(), _Eptr, idx)`где `_Eptr` объект внутренний к функции. Если `str.c_str() == *_Eptr`он бросает объект типа. `invalid_argument` Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является `*_Eptr -  str.c_str()` `*idx` нулевой указатель, функция хранит и возвращает значение.

## <a name="stoul"></a><a name="stoul"></a>stoul

Преобразует последовательность символов в длинное целое без знака.

```cpp
unsigned long stoul(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long stoul(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Параметры

*Ул*\
Последовательность символов для преобразования.

*Idx*\
Значение индекса первого непреобразованного символа.

*Базы*\
Используемое числовое основание.

### <a name="return-value"></a>Возвращаемое значение

Длинное целое значение без знака.

### <a name="remarks"></a>Remarks

Функция преобразует последовательность элементов в *str* в **`unsigned long`** значение типа, как будто вызывая, `strtoul( str.c_str(), _Eptr, idx)`где `_Eptr` объект внутренний к функции. Если `str.c_str() == *_Eptr`он бросает объект типа. `invalid_argument` Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является `*_Eptr -  str.c_str()` `*idx` нулевой указатель, функция хранит и возвращает значение.

## <a name="stoull"></a><a name="stoull"></a>stoull

Преобразует последовательность символов **`unsigned long long`** в .

```cpp
unsigned long long stoull(
    const string& str,
    size_t* idx = 0,
    int base = 10);

unsigned long long stoull(
    const wstring& str,
    size_t* idx = 0,
    int base = 10);
```

### <a name="parameters"></a>Параметры

*Ул*\
Последовательность символов для преобразования.

*Idx*\
Значение индекса первого непреобразованного символа.

*Базы*\
Используемое числовое основание.

### <a name="return-value"></a>Возвращаемое значение

Значение. **`unsigned long long`**

### <a name="remarks"></a>Remarks

Функция преобразует последовательность элементов в *str* в **`unsigned long long`** значение типа, как будто вызывая, `strtoull( str.c_str(), _Eptr, idx)`где `_Eptr` объект внутренний к функции. Если `str.c_str() == *_Eptr`он бросает объект типа. `invalid_argument` Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является `*_Eptr -  str.c_str()` `*idx` нулевой указатель, функция хранит и возвращает значение.

## <a name="swap"></a><a name="swap"></a>Своп

Меняет местами массивы символов двух строк.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Левой*\
Одна строка, элементы которой должны быть заменены с элементами другой строки.

*Правильно*\
Другая строка, элементы которой будут заменены на элементы первой строки.

### <a name="remarks"></a>Remarks

Функция шаблона выполняет функцию специализированного члена *слева.* [своп](../standard-library/basic-string-class.md#swap)*(справа)* для строк, что гарантирует постоянную сложность.

### <a name="example"></a>Пример

```cpp
// string_swap.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an object of type basic_string<char>
   string s1 ( "Tweedledee" );
   string s2 ( "Tweedledum" );
   cout << "Before swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   swap ( s1 , s2 );
   cout << "\nAfter swapping string s1 and s2:" << endl;
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;
}
```

```Output
Before swapping string s1 and s2:
The basic_string s1 = Tweedledee.
The basic_string s2 = Tweedledum.

After swapping string s1 and s2:
The basic_string s1 = Tweedledum.
The basic_string s2 = Tweedledee.
```

## <a name="to_string"></a><a name="to_string"></a>to_string

Преобразует значение в `string`.

```cpp
string to_string(int value);
string to_string(unsigned int value);
string to_string(long value);
string to_string(unsigned long value);
string to_string(long long value);
string to_string(unsigned long long value);
string to_string(float value);
string to_string(double value);
string to_string(long double value);
```

### <a name="parameters"></a>Параметры

*Значение*\
Преобразуемое значение.

### <a name="return-value"></a>Возвращаемое значение

Объект `string`, представляющий значение.

### <a name="remarks"></a>Remarks

Функция преобразует *значение* в последовательность элементов, `Buf` хранящихся в объекте массива внутри функции, как будто вызывая, `sprintf(Buf, Fmt, value)`где `Fmt`

- `"%d"`если *значение* типа**`int`**

- `"%u"`если *значение* типа**`unsigned int`**

- `"%ld"`если *значение* типа**`long`**

- `"%lu"`если *значение* типа**`unsigned long`**

- `"%lld"`если *значение* типа**`long long`**

- `"%llu"`если *значение* типа**`unsigned long long`**

- `"%f"`если *значение* имеет **`float`** тип или**`double`**

- `"%Lf"`если *значение* типа**`long double`**

Функция возвращает `string(Buf)`.

## <a name="to_wstring"></a><a name="to_wstring"></a>to_wstring

Преобразует значение в расширенную строку.

```cpp
wstring to_wstring(int value);
wstring to_wstring(unsigned int value);
wstring to_wstring(long value);
wstring to_wstring(unsigned long value);
wstring to_wstring(long long value);
wstring to_wstring(unsigned long long value);
wstring to_wstring(float value);
wstring to_wstring(double value);
wstring to_wstring(long double value);
```

### <a name="parameters"></a>Параметры

*Значение*\
Преобразуемое значение.

### <a name="return-value"></a>Возвращаемое значение

Расширенная строка, представляющая значение.

### <a name="remarks"></a>Remarks

Функция преобразует *значение* в последовательность элементов, `Buf` хранящихся в объекте массива внутри функции, как будто вызывая, `swprintf(Buf, Len, Fmt, value)`где `Fmt`

- `L"%d"`если *значение* типа**`int`**

- `L"%u"`если *значение* типа**`unsigned int`**

- `L"%ld"`если *значение* типа**`long`**

- `L"%lu"`если *значение* типа**`unsigned long`**

- `L"%lld"`если *значение* типа**`long long`**

- `L"%llu"`если *значение* типа**`unsigned long long`**

- `L"%f"`если *значение* имеет **`float`** тип или**`double`**

- `L"%Lf"`если *значение* типа**`long double`**

Функция возвращает `wstring(Buf)`.

## <a name="see-also"></a>См. также раздел

[\<струнная>](../standard-library/string.md)
