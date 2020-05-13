---
title: Класс basic_regex
ms.date: 03/27/2019
f1_keywords:
- regex/std::basic_regex
helpviewer_keywords:
- basic_regex class
ms.assetid: 8a18c6b4-f22a-4cfd-bc16-b4267867ebc3
ms.openlocfilehash: 74a8684c619e2cfbd5417950aa6108ad93511bf7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376749"
---
# <a name="basic_regex-class"></a>Класс basic_regex

Создание оболочки для регулярного выражения.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Elem, class RXtraits>
class basic_regex
```

## <a name="parameters"></a>Параметры

*Elem*\
Тип элементов для обеспечения соответствия.

*RXtraits*\
Класс характеристик для элементов.

## <a name="remarks"></a>Remarks

Шаблон класса описывает объект, в мещавхом выражении. Объекты этого шаблона класса могут быть переданы в шаблон функции [regex_match,](../standard-library/regex-functions.md#regex_match) [regex_search](../standard-library/regex-functions.md#regex_search)и [regex_replace,](../standard-library/regex-functions.md#regex_replace)наряду с подходящими аргументами строки текста, для поиска текста, который соответствует обычному выражению. Есть две специализации этого шаблона класса, с определением типа [regex](../standard-library/regex-typedefs.md#regex) для элементов типа **char,** и [wregex](../standard-library/regex-typedefs.md#wregex) для элементов типа **wchar_t.**

Аргумент шаблона *RXtraits* описывает различные важные свойства синтаксиса регулярных выражений, которые поддерживает шаблон класса. Класс, описавающее эти регулярные признаки выражения, должен иметь тот же внешний интерфейс, что и объект типа [regex_traits класса.](../standard-library/regex-traits-class.md)

Некоторые функции принимают последовательность операндов, определяющую регулярное выражение. Такую последовательность операндов можно задать несколькими способами:

`ptr`-- нулевая последовательность (например, строка C, для `ptr` *Elem* of type **char),** начинающаяся (которая не должна `value_type()` быть нулевой указкой), где термин омрачающий элемент является значением и не является частью последовательности действий

`ptr`, `count` -- последовательность элементов `count`, начиная с `ptr` (это должен быть не пустой указатель)

`str` -- последовательность, заданная объектом `basic_string``str`

`first`, `last` -- последовательность элементов, разделенная итераторами `first` и `last`, в диапазоне `[first, last)`

`right` -- объект `basic_regex``right`

Эти функции членов `flags` также принимают аргумент, который определяет различные варианты для интерпретации регулярного выражения в дополнение к тем, которые описаны типом *RXtraits.*

### <a name="members"></a>Участники

|Участник|Значение по умолчанию|
|-|-|
|общественный статического const flag_type icase|regex_constants::icase|
|общественный статический const flag_type nosubs|regex_constants::nosubs|
|общественный статического const flag_type оптимизировать|regex_constants::оптимизация|
|общественный статического const flag_type collate|regex_constants::collate|
|публичный статический const flag_type ECMAScript|regex_constants:ECMAScript|
|общественный статического const flag_type основные|regex_constants::основной|
|общественный статического const flag_type расширен|regex_constants::расширенный|
|общественный статический Const flag_type awk|regex_constants::awk|
|общественный статического const flag_type grep|regex_constants::grep|
|общественный статических Const flag_type egrep|regex_constants::egrep|
|частные черты RXtraits||

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_regex](#basic_regex)|Конструирует объект регулярного выражения.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[flag_type](#flag_type)|Тип флагов параметров синтаксиса.|
|[locale_type](#locale_type)|Тип сохраненного объекта языкового стандарта.|
|[Value_type](#value_type)|Тип элемента.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[Назначить](#assign)|Присваивает значение объекту регулярного выражения.|
|[Флаги](#flags)|Возвращает флаги параметров синтаксиса.|
|[getloc](#getloc)|Возвращает сохраненный объект языкового стандарта.|
|[imbue](#imbue)|Изменяет сохраненный объект языкового стандарта.|
|[mark_count](#mark_count)|Возвращает число сопоставленных частей выражения.|
|[Своп](#swap)|Меняет местами два объекта регулярного выражения.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператора](#op_eq)|Присваивает значение объекту регулярного выражения.|

## <a name="requirements"></a>Требования

**Заголовок:** \<regex>

**Пространство имен:** std

## <a name="example"></a>Пример

```cpp
// std__regex__basic_regex.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

using namespace std;

int main()
{
    regex::value_type elem = 'x';
    regex::flag_type flag = regex::grep;

    elem = elem;  // to quiet "unused" warnings
    flag = flag;

    // constructors
    regex rx0;
    cout << "match(\"abc\", \"\") == " << boolalpha
        << regex_match("abc", rx0) << endl;

    regex rx1("abcd", regex::ECMAScript);
    cout << "match(\"abc\", \"abcd\") == " << boolalpha
        << regex_match("abc", rx1) << endl;

    regex rx2("abcd", 3);
    cout << "match(\"abc\", \"abc\") == " << boolalpha
        << regex_match("abc", rx2) << endl;

    regex rx3(rx2);
    cout << "match(\"abc\", \"abc\") == " << boolalpha
        << regex_match("abc", rx3) << endl;

    string str("abcd");
    regex rx4(str);
    cout << "match(string(\"abcd\"), \"abc\") == " << boolalpha
        << regex_match("abc", rx4) << endl;

    regex rx5(str.begin(), str.end() - 1);
    cout << "match(string(\"abc\"), \"abc\") == " << boolalpha
        << regex_match("abc", rx5) << endl;
    cout << endl;

    // assignments
    rx0 = "abc";
    rx0 = rx1;
    rx0 = str;

    rx0.assign("abcd", regex::ECMAScript);
    rx0.assign("abcd", 3);
    rx0.assign(rx1);
    rx0.assign(str);
    rx0.assign(str.begin(), str.end() - 1);

    rx0.swap(rx1);

    // mark_count
    cout << "\"abc\" mark_count == "
        << regex("abc").mark_count() << endl;
    cout << "\"(abc)\" mark_count == "
        << regex("(abc)").mark_count() << endl;

    // locales
    regex::locale_type loc = rx0.imbue(locale());
    cout << "getloc == imbued == " << boolalpha
        << (loc == rx0.getloc()) << endl;

    // initializer_list
    regex rx6({ 'a', 'b', 'c' }, regex::ECMAScript);
    cout << "match(\"abc\") == " << boolalpha
        << regex_match("abc", rx6);
    cout << endl;
}
```

```Output
match("abc", "") == false
match("abc", "abcd") == false
match("abc", "abc") == true
match("abc", "abc") == true
match(string("abcd"), "abc") == false
match(string("abc"), "abc") == true

"abc" mark_count == 0
"(abc)" mark_count == 1
getloc == imbued == true
match("abc") == true
```

## <a name="basic_regexassign"></a><a name="assign"></a>basic_regex::assign

Присваивает значение объекту регулярного выражения.

```cpp
basic_regex& assign(
    const basic_regex& right);

basic_regex& assign(
    const Elem* ptr,
    flag_type flags = ECMAScript);

basic_regex& assign(
    const Elem* ptr,
    size_type len,
    flag_type flags = ECMAScript);

basic_regex& assign(
    initializer_list<_Elem> IList,
    flag_type flags = regex_constants::ECMAScript);

template <class STtraits, class STalloc>
basic_regex& assign(
    const basic_string<Elem, STtraits, STalloc>& str,
    flag_type flags = ECMAScript);

template <class InIt>
basic_regex& assign(
    InIt first, InIt last,
    flag_type flags = ECMAScript);
```

### <a name="parameters"></a>Параметры

*STtraits*\
Класс признаков для источника строки.

*Штлок*\
Класс распределителя для источника строки.

*Init*\
Тип итератора ввода для источника диапазона.

*Правильно*\
Копируемый источник регулярного выражения.

*Ptr*\
Копируемый указатель на начало последовательности.

*Флаги*\
Добавляемые при копировании флаги вариантов синтаксиса.

*len/TD>*\
Копируемый конец последовательности.

*Ул*\
Копируемая строка.

*Первый*\
Копируемое начало последовательности.

*Последний*\
Копируемый конец последовательности.

*Ilist*\
Копируемый initializer_list.

### <a name="remarks"></a>Remarks

Каждая функция-член заменяет регулярное выражение, хранящееся в `*this`, на регулярное выражение, описываемое последовательностью операндов, а затем возвращает `*this`.

## <a name="basic_regexbasic_regex"></a><a name="basic_regex"></a>basic_regex::basic_regex

Конструирует объект регулярного выражения.

```cpp
basic_regex();

explicit basic_regex(
    const Elem* ptr,
    flag_type flags);

explicit basic_regex(
    const Elem* ptr,
    size_type len,
    flag_type flags);

basic_regex(
    const basic_regex& right);

basic_regex(
    initializer_list<Type> IList,
    flag_type flags);

template <class STtraits, class STalloc>
explicit basic_regex(
    const basic_string<Elem, STtraits, STalloc>& str,
    flag_type flags);

template <class InIt>
explicit basic_regex(
    InIt first,
    InIt last,
    flag_type flags);
```

### <a name="parameters"></a>Параметры

*STtraits*\
Класс признаков для источника строки.

*Штлок*\
Класс распределителя для источника строки.

*Init*\
Тип итератора ввода для источника диапазона.

*Правильно*\
Копируемый источник регулярного выражения.

*Ptr*\
Копируемый указатель на начало последовательности.

*Флаги*\
Добавляемые при копировании флаги вариантов синтаксиса.

*len/TD>*\
Копируемый конец последовательности.

*Ул*\
Копируемая строка.

*Первый*\
Копируемое начало последовательности.

*Последний*\
Копируемый конец последовательности.

*Ilist*\
Копируемый initializer_list.

### <a name="remarks"></a>Remarks

Все последовательности хранят объект типа `RXtraits`, сконструированный по умолчанию.

Первый конструктор создает пустой объект `basic_regex`. Другие конструкторы создают объект `basic_regex`, который содержит регулярное выражение, описанное последовательностью операндов.

Пустой `basic_regex` объект не соответствует последовательности символов при передаваемом [regex_match,](../standard-library/regex-functions.md#regex_match) [regex_search](../standard-library/regex-functions.md#regex_search)или [regex_replace.](../standard-library/regex-functions.md#regex_replace)

## <a name="basic_regexflag_type"></a><a name="flag_type"></a>basic_regex:::flag_type

Тип флагов параметров синтаксиса.

```cpp
typedef regex_constants::syntax_option_type flag_type;
```

### <a name="remarks"></a>Remarks

Этот тип является синонимом [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type).

## <a name="basic_regexflags"></a><a name="flags"></a>basic_regex::флаги

Возвращает флаги параметров синтаксиса.

```cpp
flag_type flags() const;
```

### <a name="remarks"></a>Remarks

Эта функция-член возвращает значение аргумента `flag_type`, переданного в последний вызов одной из функций-членов [basic_regex::assign](#assign), или, если вызовы не выполнялись, возвращает значение, переданное в конструктор.

## <a name="basic_regexgetloc"></a><a name="getloc"></a>basic_regex::getloc

Возвращает сохраненный объект языкового стандарта.

```cpp
locale_type getloc() const;
```

### <a name="remarks"></a>Remarks

Функция участника `traits.` [возвращается regex_traits::getloc](../standard-library/regex-traits-class.md#getloc)`()`.

## <a name="basic_regeximbue"></a><a name="imbue"></a>basic_regex::imbue

Изменяет сохраненный объект языкового стандарта.

```cpp
locale_type imbue(locale_type loc);
```

### <a name="parameters"></a>Параметры

*Loc*\
Объект языкового стандарта, который необходимо сохранить.

### <a name="remarks"></a>Remarks

Функция члена `*this` опорожняет и возвращает `traits.` [regex_traits::imbue](../standard-library/regex-traits-class.md#imbue)`(loc)`.

## <a name="basic_regexlocale_type"></a><a name="locale_type"></a>basic_regex::locale_type

Тип сохраненного объекта языкового стандарта.

```cpp
typedef typename RXtraits::locale_type locale_type;
```

### <a name="remarks"></a>Remarks

Этот тип является синонимом [regex_traits::locale_type](../standard-library/regex-traits-class.md#locale_type).

## <a name="basic_regexmark_count"></a><a name="mark_count"></a>basic_regex::mark_count

Возвращает число сопоставленных частей выражения.

```cpp
unsigned mark_count() const;
```

### <a name="remarks"></a>Remarks

Функция-член возвращает число групп записи в регулярном выражении.

## <a name="basic_regexoperator"></a><a name="op_eq"></a>basic_regex:оператор

Присваивает значение объекту регулярного выражения.

```cpp
basic_regex& operator=(const basic_regex& right);

basic_regex& operator=(const Elem *str);

template <class STtraits, class STalloc>
basic_regex& operator=(const basic_string<Elem, STtraits, STalloc>& str);
```

### <a name="parameters"></a>Параметры

*STtraits*\
Класс признаков для источника строки.

*Штлок*\
Класс распределителя для источника строки.

*Правильно*\
Копируемый источник регулярного выражения.

*Ул*\
Копируемая строка.

### <a name="remarks"></a>Remarks

Каждый оператор заменяет регулярное выражение, хранящееся в `*this` , на регулярное выражение, описываемое последовательностью операндов, а затем возвращает `*this`.

## <a name="basic_regexswap"></a><a name="swap"></a>basic_regex::swap

Меняет местами два объекта регулярного выражения.

```cpp
void swap(basic_regex& right) throw();
```

### <a name="parameters"></a>Параметры

*Правильно*\
Объект регулярного выражения для замены.

### <a name="remarks"></a>Remarks

Функция члена меняет регулярные выражения `*this` между и *правыми.* Она делает это в константном времени и не создает исключений.

## <a name="basic_regexvalue_type"></a><a name="value_type"></a>basic_regex::value_type

Тип элемента.

```cpp
typedef Elem value_type;
```

### <a name="remarks"></a>Remarks

Тип является синонимом параметра *шаблона Elem.*

## <a name="see-also"></a>См. также раздел

[\<regex>](../standard-library/regex.md)\
[regex_match](../standard-library/regex-functions.md#regex_match)\
[regex_search](../standard-library/regex-functions.md#regex_search)\
[regex_replace](../standard-library/regex-functions.md#regex_replace)\
[Regex](../standard-library/regex-typedefs.md#regex)\
[wregex](../standard-library/regex-typedefs.md#wregex)\
[Класс regex_traits](../standard-library/regex-traits-class.md)
