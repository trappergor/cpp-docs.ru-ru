---
title: Функции &lt;string&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
author: corob-msft
ms.author: corob
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
ms.workload:
- cplusplus
ms.openlocfilehash: 6534d93b4f04826188fa13c942efd080e152aebe
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954907"
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

*является* входной поток, из которого будет извлекаться строка.

*STR* строку, в которую считываются символы из входного потока.

*delim* разделитель строк.

### <a name="return-value"></a>Возвращаемое значение

Входной поток *является*.

### <a name="remarks"></a>Примечания

Пара подписей функций, обозначенных как `(1)` извлекает символы из *—* пока *delim* обнаруживается, хранить их в *str*.

Пара подписей функций, обозначенных как `(2)` использует символ новой строки как разделитель строки по умолчанию и работает как **getline**(`is`, `str`, `is`. `widen`(' `\n`')).

Вторая функция каждой пары аналогична первой и поддерживает [ссылки rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md).

Извлечение останавливается при возникновении одного из следующих условий.

- В конец файла в этом случае внутренний флаг состояния *—* присваивается `ios_base::eofbit`.

- после того как функция извлечет элемент, который оценивается как эквивалентный `delim`, и в этом случае элемент не возвращается и не добавляется в управляемую последовательность;

- Затем функция извлекает `str.` [max_size](../standard-library/basic-string-class.md#max_size) элементов, в этом случае внутренний флаг состояния *—* присваивается `ios_base::failbit`.

- Некоторые ошибки, отличные от перечисленных выше, в этом случае внутренний флаг состояния *является* имеет значение `ios_base::badbit`

Сведения о внутренних флагах состояния см. в разделе [ios_base::iostate](../standard-library/ios-base-class.md#iostate).

Если функция не извлекает ни один элемент, внутренний флаг состояния *—* присваивается `ios_base::failbit`. В любом случае `getline` возвращает *является*.

Если создается исключение, *—* и *str* остаются в допустимом состоянии.

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

Преобразует последовательность символов **двойные**.

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

|Параметр|Описание:|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Значение индекса первого непреобразованного символа.|

### <a name="return-value"></a>Возвращаемое значение

**Двойные** значение.

### <a name="remarks"></a>Примечания

Функция преобразует последовательность элементов в *str* значение `val` типа **двойные** как при вызове `strtod( str.c_str(), _Eptr)`, где `_Eptr` — это объект, размещенного внутри функции. Если ` str.c_str() == *_Eptr`, то создается объект типа `invalid_argument`. Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает `val`.

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

|Параметр|Описание:|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Значение индекса первого непреобразованного символа.|

### <a name="return-value"></a>Возвращаемое значение

Значение с плавающей запятой.

### <a name="remarks"></a>Примечания

Функция преобразует последовательность элементов в *str* значение `val` типа **float** как при вызове `strtof( str.c_str(), _Eptr)`, где `_Eptr` — это объект, размещенного внутри функции. Если ` str.c_str() == *_Eptr`, то создается объект типа `invalid_argument`. Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает `val`.

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

|Параметр|Описание:|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Содержит индекс первого возвращенного непреобразованного символа.|
|*base*|Используемое числовое основание.|

### <a name="remarks"></a>Примечания

Функция `stoi` преобразует последовательность символов в *str* значение типа **int** и возвращает значение. Например, если передать последовательность символов "10", `stoi` возвращает целочисленное значение 10.

`stoi` работает аналогично функции `strtol` для однобайтовых символов при вызове `strtol( str.c_str(), _Eptr, idx)`, где `_Eptr` — внутренний объект функции; или `wcstol` для двухбайтовых символов при вызове `wcstol(Str.c_str(), _Eptr, idx)`. Дополнительные сведения см. в разделе [strtol, wcstol, _strtol_l, _wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md).

Если `str.c_str() == *_Eptr`, `stoi` создается объект типа `invalid_argument`. Если такой вызов задает `errno`, или если возвращаемое значение не может быть представлено в виде объекта типа **int**, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr - str.c_str()` в `*idx`.

## <a name="stol"></a>  stol

Преобразует последовательность символов **long**.

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

|Параметр|Описание:|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Значение индекса первого непреобразованного символа.|
|*base*|Используемое числовое основание.|

### <a name="return-value"></a>Возвращаемое значение

Длинное целое значение.

### <a name="remarks"></a>Примечания

Функция преобразует последовательность элементов в *str* значение `val` типа **long** как при вызове `strtol( str.c_str(), _Eptr, idx)`, где `_Eptr` — это объект, размещенного внутри функции. Если ` str.c_str() == *_Eptr`, то создается объект типа `invalid_argument`. Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает `val`.

## <a name="stold"></a>  stold

Преобразует последовательность символов **long double**.

```cpp
double stold(
    const string& str,
    size_t* idx = 0);

double stold(
    const wstring& str,
    size_t* idx = 0);
```

### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Значение индекса первого непреобразованного символа.|

### <a name="return-value"></a>Возвращаемое значение

**Long double** значение.

### <a name="remarks"></a>Примечания

Функция преобразует последовательность элементов в *str* значение `val` типа **long double** как при вызове `strtold( str.c_str(), _Eptr)`, где `_Eptr` — это объект, размещенного внутри функции. Если ` str.c_str() == *_Eptr`, то создается объект типа `invalid_argument`. Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает `val`.

## <a name="stoll"></a>  stoll

Преобразует последовательность символов **long long**.

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

|Параметр|Описание:|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Значение индекса первого непреобразованного символа.|
|*base*|Используемое числовое основание.|

### <a name="return-value"></a>Возвращаемое значение

**Long long** значение.

### <a name="remarks"></a>Примечания

Функция преобразует последовательность элементов в *str* значение `val` типа **long long** как при вызове `strtoll( str.c_str(), _Eptr, idx)`, где `_Eptr` — это объект, размещенного внутри функции. Если ` str.c_str() == *_Eptr`, то создается объект типа `invalid_argument`. Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает `val`.

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

|Параметр|Описание:|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Значение индекса первого непреобразованного символа.|
|*base*|Используемое числовое основание.|

### <a name="return-value"></a>Возвращаемое значение

Длинное целое значение без знака.

### <a name="remarks"></a>Примечания

Функция преобразует последовательность элементов в *str* значение `val` типа **unsigned long** как при вызове `strtoul( str.c_str(), _Eptr, idx)`, где `_Eptr` — это объект, размещенного внутри функции . Если ` str.c_str() == *_Eptr`, то создается объект типа `invalid_argument`. Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает `val`.

## <a name="stoull"></a>  stoull

Преобразует последовательность символов **long long без знака**.

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

|Параметр|Описание:|
|---------------|-----------------|
|*str*|Последовательность символов для преобразования.|
|*IDX*|Значение индекса первого непреобразованного символа.|
|*base*|Используемое числовое основание.|

### <a name="return-value"></a>Возвращаемое значение

**Long long без знака** значение.

### <a name="remarks"></a>Примечания

Функция преобразует последовательность элементов в *str* значение `val` типа **long long без знака** как при вызове `strtoull( str.c_str(), _Eptr, idx)`, где `_Eptr` является внутренним для объекта функция. Если ` str.c_str() == *_Eptr`, то создается объект типа `invalid_argument`. Если такой вызов задает `errno`, то создается объект типа `out_of_range`. В противном случае, если *idx* не является пустым указателем, функция сохраняет `*_Eptr -  str.c_str()` в `*idx` и возвращает `val`.

## <a name="swap"></a>  swap

Меняет местами массивы символов двух строк.

```cpp
template <class Traits, class Allocator>
void swap(basic_string<CharType, Traits, Allocator>& left, basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*слева* одна строка, элементы которого должны быть заменены другой строкой.

*правом* другая строка, элементы которого должны быть поменять местами с первой строки.

### <a name="remarks"></a>Примечания

Эта функция шаблона выполняет функцию-член специализированные *левой*.[ Переключение](../standard-library/basic-string-class.md#swap)(*правой*) для строк, что гарантирует постоянную сложность.

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

|Параметр|Описание:|
|---------------|-----------------|
|*Val*|Преобразуемое значение.|

### <a name="return-value"></a>Возвращаемое значение

Объект `string`, представляющий значение.

### <a name="remarks"></a>Примечания

Функция преобразует *Val* в последовательность элементов, сохраненную в объекте массива `Buf` внутренней функции, как при вызове `sprintf(Buf, Fmt, Val)`, где `Fmt` —

- `"%d"` Если `Val` имеет тип **int**

- `"%u"` Если `Val` имеет тип **типа int без знака**

- `"%ld"` Если `Val` имеет тип **long**

- `"%lu"` Если `Val` имеет тип **unsigned long**

- `"%lld"` Если `Val` имеет тип **long long**

- `"%llu"` Если `Val` имеет тип **long long без знака**

- `"%f"` Если `Val` имеет тип **float** или **double**

- `"%Lf"` Если `Val` имеет тип **long double**

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

|Параметр|Описание|
|---------------|-----------------|
|`Val`|Преобразуемое значение.|

### <a name="return-value"></a>Возвращаемое значение

Расширенная строка, представляющая значение.

### <a name="remarks"></a>Примечания

Эта функция преобразовывает `Val` в последовательность элементов, хранящихся в объекте массива `Buf`, размещенного внутри функции, как если бы выполнялся вызов `swprintf(Buf, Len, Fmt, Val)`, где `Fmt` равняется

- `L"%d"` Если `Val` имеет тип **int**

- `L"%u"` Если `Val` имеет тип **типа int без знака**

- `L"%ld"` Если `Val` имеет тип **long**

- `L"%lu"` Если `Val` имеет тип **unsigned long**

- `L"%lld"` Если `Val` имеет тип **long long**

- `L"%llu"` Если `Val` имеет тип **long long без знака**

- `L"%f"` Если `Val` имеет тип **float** или **double**

- `L"%Lf"` Если `Val` имеет тип **long double**

Функция возвращает `wstring(Buf)`.

## <a name="see-also"></a>См. также

[\<string>](../standard-library/string.md)<br/>
