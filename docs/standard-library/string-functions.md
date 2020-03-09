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
ms.openlocfilehash: 828aeb975178850f5c0a7ea3b7e982bbadd6e7c4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856618"
---
# <a name="ltstringgt-functions"></a>Функции &lt;string&gt;

||||
|-|-|-|
|[getline](#getline)|[stod](#stod)|[stof](#stof)|
|[stoi](#stoi)|[stol](#stol)|[stold](#stold)|
|[stoll](#stoll)|[stoul](#stoul)|[stoull](#stoull)|
|[swap](#swap)|[to_string](#to_string)|[to_wstring](#to_wstring)|

## <a name="getline"></a>  getline

Извлекает строки из входного потока, последовательно по одной строке.

```cpp
// (1) delimiter as parameter
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str,
    CharType delim);

template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>&& is,
    basic_string<CharType, Traits, Allocator>& str,
    const CharType delim);

// (2) default delimiter used
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& getline(
    basic_istream<CharType, Traits>& is,
    basic_string<CharType, Traits, Allocator>& str);

template <class Allocator, class Traits, class Allocator>
basic_istream<Allocator, Traits>& getline(
    basic_istream<Allocator, Traits>&& is,
    basic_string<Allocator, Traits, Allocator>& str);
```

### <a name="parameters"></a>Параметры

*is*\
Входной поток, из которого извлекается строка.

\ *str*
Строка, в которую считываются символы из входного потока.

*delim*\
Разделитель строк.

### <a name="return-value"></a>Возвращаемое значение

Входной поток *—*.

### <a name="remarks"></a>Remarks

Пара подписей функций, помеченных `(1)` извлечения символов из *,* до тех пор, пока не будет найден *delim* , сохраняя их в *str*.

Пара подписей функций, помеченных `(2)`, использует новую строку в качестве разделителя по умолчанию и ведет себя как во **встроенном**(`is`, `str`, `is`. `widen`(' `\n`')).

Вторая функция каждой пары аналогична первой и поддерживает [ссылки rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md).

Извлечение останавливается при возникновении одного из следующих условий.

- В конце файла, в этом случае флаг внутреннего состояния *имеет* значение `ios_base::eofbit`.

- после того как функция извлечет элемент, который оценивается как эквивалентный `delim`, и в этом случае элемент не возвращается и не добавляется в управляемую последовательность;

- После того как функция извлекает `str.`[max_size](../standard-library/basic-string-class.md#max_size) элементы, в этом случае флаг внутреннего состояния *имеет* значение `ios_base::failbit`.

- Другая ошибка, отличная от перечисленных ранее. в этом случае флаг внутреннего состояния *имеет* значение `ios_base::badbit`

Сведения о внутренних флагах состояния см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

Если функция не извлекает ни одного элемента, флаг внутреннего состояния *имеет* значение `ios_base::failbit`. В любом случае `getline` возвращает *значение*.

Если возникает исключение, *то имеет значение* , а *str* остается в допустимом состоянии.

### <a name="example"></a>Пример

Следующий код демонстрирует `getline()` в двух режимах: в первом с разделителем — символом новой строки (по умолчанию), во втором с разделителем — пробелом. Символ конца файла (CTRL-Z на клавиатуре) используется для управления завершением циклов while. При этом внутренний флаг состояния `cin` устанавливается в значение `eofbit`, которое необходимо очистить с помощью [basic_ios::clear()](../standard-library/basic-ios-class.md#clear), чтобы второй цикл while мог правильно работать.

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

## <a name="stod"></a>  stod

Преобразует последовательность символов в значение **типа Double**.

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

|Параметр|Description|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Значение индекса первого непреобразованного символа.|

### <a name="return-value"></a>Возвращаемое значение

Значение **типа Double** .

### <a name="remarks"></a>Remarks

Функция преобразует последовательность элементов в *str* в значение `val` типа **Double** , как при вызове `strtod( str.c_str(), _Eptr)`, где `_Eptr` является объектом, внутренним с функцией. Если ` str.c_str() == *_Eptr`, то создается объект типа `invalid_argument`. Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает `val`.

## <a name="stof"></a>  stof

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

|Параметр|Description|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Значение индекса первого непреобразованного символа.|

### <a name="return-value"></a>Возвращаемое значение

Значение с плавающей запятой.

### <a name="remarks"></a>Remarks

Функция преобразует последовательность элементов в *str* в значение `val` типа **float** , как при вызове `strtof( str.c_str(), _Eptr)`, где `_Eptr` является объектом, внутренним с функцией. Если ` str.c_str() == *_Eptr`, то создается объект типа `invalid_argument`. Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает `val`.

## <a name="stoi"></a>  stoi

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

|Параметр|Description|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Содержит индекс первого возвращенного непреобразованного символа.|
|*base*|Используемое числовое основание.|

### <a name="remarks"></a>Remarks

Функция `stoi` преобразует последовательность символов в *str* в значение типа **int** и возвращает значение. Например, если передать последовательность символов "10", `stoi` возвращает целочисленное значение 10.

`stoi` работает аналогично функции `strtol` для однобайтовых символов при вызове `strtol( str.c_str(), _Eptr, idx)`, где `_Eptr` — внутренний объект функции; или `wcstol` для двухбайтовых символов при вызове `wcstol(Str.c_str(), _Eptr, idx)`. Дополнительные сведения см. в разделе [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md).

Если `str.c_str() == *_Eptr`, `stoi` создает объект типа `invalid_argument`. Если такой вызов будет установлен `errno`или если возвращаемое значение не может быть представлено в виде объекта типа **int**, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr - str.c_str()` в `*idx`.

## <a name="stol"></a>  stol

Преобразует последовательность символов в значение **типа Long**.

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

|Параметр|Description|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Значение индекса первого непреобразованного символа.|
|*base*|Используемое числовое основание.|

### <a name="return-value"></a>Возвращаемое значение

Длинное целое значение.

### <a name="remarks"></a>Remarks

Функция преобразует последовательность элементов в *str* в значение `val` типа **Long** , если выполняется вызов `strtol( str.c_str(), _Eptr, idx)`, где `_Eptr` является объектом, внутренним с функцией. Если ` str.c_str() == *_Eptr`, то создается объект типа `invalid_argument`. Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает `val`.

## <a name="stold"></a>  stold

Преобразует последовательность символов в **длинное двойное**значение.

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Параметры

|Параметр|Description|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Значение индекса первого непреобразованного символа.|

### <a name="return-value"></a>Возвращаемое значение

**Длинное двойное** значение.

### <a name="remarks"></a>Remarks

Функция преобразует последовательность элементов в *str* в значение `val` типа **long double** , как при вызове `strtold( str.c_str(), _Eptr)`, где `_Eptr` является объектом, внутренним с функцией. Если ` str.c_str() == *_Eptr`, то создается объект типа `invalid_argument`. Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает `val`.

## <a name="stoll"></a>  stoll

Преобразует последовательность символов в **длинную длину**.

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

|Параметр|Description|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Значение индекса первого непреобразованного символа.|
|*base*|Используемое числовое основание.|

### <a name="return-value"></a>Возвращаемое значение

**Длинное** значение long.

### <a name="remarks"></a>Remarks

Функция преобразует последовательность элементов в *str* в значение `val` типа **Long** , если при вызове `strtoll( str.c_str(), _Eptr, idx)`, где `_Eptr` является объектом, внутренним с функцией. Если ` str.c_str() == *_Eptr`, то создается объект типа `invalid_argument`. Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает `val`.

## <a name="stoul"></a>  stoul

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

|Параметр|Description|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Значение индекса первого непреобразованного символа.|
|*base*|Используемое числовое основание.|

### <a name="return-value"></a>Возвращаемое значение

Длинное целое значение без знака.

### <a name="remarks"></a>Remarks

Функция преобразует последовательность элементов в *str* в значение `val` типа **без знака** , как если бы он вызывал `strtoul( str.c_str(), _Eptr, idx)`, где `_Eptr` является объектом, внутренним с функцией. Если ` str.c_str() == *_Eptr`, то создается объект типа `invalid_argument`. Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает `val`.

## <a name="stoull"></a>  stoull

Преобразует последовательность символов в **длинную длину без знака**.

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

|Параметр|Description|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Значение индекса первого непреобразованного символа.|
|*base*|Используемое числовое основание.|

### <a name="return-value"></a>Возвращаемое значение

Длинное целое значение **без знака** .

### <a name="remarks"></a>Remarks

Функция преобразует последовательность элементов в *str* в значение `val` типа **без знака Long** , как если бы вызывался метод `strtoull( str.c_str(), _Eptr, idx)`, где `_Eptr` является объектом, внутренним с функцией. Если ` str.c_str() == *_Eptr`, то создается объект типа `invalid_argument`. Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает `val`.

## <a name="swap"></a>  swap

Меняет местами массивы символов двух строк.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*left*\
Одна строка, элементы которой будут заменены на элементы другой строки.

*справа*\
Другая строка, элементы которой будут заменены на элементы первой строки.

### <a name="remarks"></a>Remarks

Функция шаблона выполняет специализированную функцию члена *Left*. [Переключение](../standard-library/basic-string-class.md#swap)(*right*) для строк, что гарантирует постоянную сложность.

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

## <a name="to_string"></a>  to_string

Преобразует значение в `string`.

```cpp
string to_string(int Val);
string to_string(unsigned int Val);
string to_string(long Val);
string to_string(unsigned long Val);
string to_string(long long Val);
string to_string(unsigned long long Val);
string to_string(float Val);
string to_string(double Val);
string to_string(long double Val);
```

### <a name="parameters"></a>Параметры

|Параметр|Description|
|---------------|-----------------|
|*Val*|Преобразуемое значение.|

### <a name="return-value"></a>Возвращаемое значение

Объект `string`, представляющий значение.

### <a name="remarks"></a>Remarks

Функция преобразует *Val* в последовательность элементов, хранящихся в объекте массива `Buf` внутренне с функцией, как при вызове `sprintf(Buf, Fmt, Val)`, где `Fmt`

- `"%d"`, если `Val` имеет тип **int**

- `"%u"`, если `Val` имеет тип **без знака int**

- `"%ld"`, если `Val` имеет тип **Long**

- `"%lu"`, если `Val` имеет тип **без знака Long**

- `"%lld"`, если `Val` имеет **тип long**

- `"%llu"`, если `Val` имеет тип **без знака** Long

- `"%f"`, если `Val` имеет тип **float** или **Double**

- `"%Lf"`, если `Val` имеет тип **long double**

Функция возвращает `string(Buf)`.

## <a name="to_wstring"></a>  to_wstring

Преобразует значение в расширенную строку.

```cpp
wstring to_wstring(int Val);
wstring to_wstring(unsigned int Val);
wstring to_wstring(long Val);
wstring to_wstring(unsigned long Val);
wstring to_wstring(long long Val);
wstring to_wstring(unsigned long long Val);
wstring to_wstring(float Val);
wstring to_wstring(double Val);
wstring to_wstring(long double Val);
```

### <a name="parameters"></a>Параметры

|Параметр|Description|
|---------------|-----------------|
|`Val`|Преобразуемое значение.|

### <a name="return-value"></a>Возвращаемое значение

Расширенная строка, представляющая значение.

### <a name="remarks"></a>Remarks

Эта функция преобразовывает `Val` в последовательность элементов, хранящихся в объекте массива `Buf`, размещенного внутри функции, как если бы выполнялся вызов `swprintf(Buf, Len, Fmt, Val)`, где `Fmt` равняется

- `L"%d"`, если `Val` имеет тип **int**

- `L"%u"`, если `Val` имеет тип **без знака int**

- `L"%ld"`, если `Val` имеет тип **Long**

- `L"%lu"`, если `Val` имеет тип **без знака Long**

- `L"%lld"`, если `Val` имеет **тип long**

- `L"%llu"`, если `Val` имеет тип **без знака** Long

- `L"%f"`, если `Val` имеет тип **float** или **Double**

- `L"%Lf"`, если `Val` имеет тип **long double**

Функция возвращает `wstring(Buf)`.

## <a name="see-also"></a>См. также раздел

[\<string>](../standard-library/string.md)
