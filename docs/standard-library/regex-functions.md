---
title: Функции &lt;regex&gt;
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_match
- regex/std::regex_replace
- regex/std::regex_search
- regex/std::swap
ms.assetid: 91a8314b-6f7c-4e33-b7d6-d8583dd75585
helpviewer_keywords:
- std::regex_match [C++]
- std::regex_replace [C++]
- std::regex_search [C++]
- std::swap [C++]
- std::swap [C++]
ms.openlocfilehash: ff6ea37208aef19431bf7aefe612dccd589c638b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374542"
---
# <a name="ltregexgt-functions"></a>Функции &lt;regex&gt;

|||
|-|-|
|[regex_match](#regex_match)|Проверяет, совпадает ли регулярное выражение со всей целевой строкой.|
|[regex_replace](#regex_replace)|Заменяет соответствующие регулярные выражения.|
|[regex_search](#regex_search)|Поиск соответствия регулярному выражению.|
|[Своп](#swap)|Свопы `basic_regex` `match_results` два или объекты.|

## <a name="regex_match"></a><a name="regex_match"></a>regex_match

Проверяет, совпадает ли регулярное выражение со всей целевой строкой.

```cpp
// (1)
template <class BidIt, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    BidIt first,
    Bidit last,
    match_results<BidIt, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (2)
template <class BidIt, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    BidIt first,
    Bidit last,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (3)
template <class Elem, class Alloc, class RXtraits, class Alloc2>
bool regex_match(
    const Elem *ptr,
    match_results<const Elem*, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (4)
template <class Elem, class RXtraits, class Alloc2>
bool regex_match(
    const Elem *ptr,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (5)
template <class IOtraits, class IOalloc, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    match_results<typename basic_string<Elem, IOtraits, IOalloc>::const_iterator, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

// (6)
template <class IOtraits, class IOalloc, class Elem, class RXtraits, class Alloc2>
bool regex_match(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);
```

### <a name="parameters"></a>Параметры

*BidIt*\
Тип итератора для подстрок соответствия. Для распространенных случаев `wstring::const_iterator` `const char*` это `const wchar_t*`один из `string::const_iterator`, или .

*Alloc*\
Класс распределителя результатов соответствия.

*Elem*\
Тип элементов для обеспечения соответствия. Для обычных `string`случаев `char*` `wchar_t*`это, `wstring`или .

*RXtraits*\
Класс характеристик для элементов.

*Аллок2*\
Класс распределителя регулярного выражения.

*Иотраиты*\
Класс характеристик строки.

*IOalloc*\
Класс распределителя строк.

*Флаги*\
Флаги для соответствий.

*Первый*\
Начало последовательности для сопоставления.

*Последний*\
Конец последовательности для сопоставления.

*Матч*\
Результаты сопоставления. Соответствует типу Elem: [матч](../standard-library/regex-typedefs.md#smatch) за `string`, [wsmatch](../standard-library/regex-typedefs.md#wsmatch) для `wstring`, `wchar_t*` [cmatch](../standard-library/regex-typedefs.md#cmatch) для `char*` или [wcmatch](../standard-library/regex-typedefs.md#wcmatch) для .

*Ptr*\
Указатель на начало последовательности для сопоставления. Если *ptr,* `char*`то `cmatch` `regex`используйте и . Если *ptr* `wchar_t*` затем `wcmatch` `wregex`использовать и .

*Повторно*\
Регулярное выражение для сопоставления. Тип `regex` `string` для `char*`и, `wstring` `wchar_t*`или `wregex` для и .

*Ул*\
Сопоставляемая строка. Соответствует типу *Elem*.

### <a name="remarks"></a>Remarks

Каждая функция шаблона возвращается верно только в том случае, если вся последовательность работы *точно* соответствует обычному аргументу выражения *re.* Используйте [regex_search,](../standard-library/regex-functions.md#regex_search) чтобы сопоставить подстроку в целевой последовательности и `regex_iterator` найти несколько совпадений. Функции, принимающие объект `match_results`, указывают в своих членах, выполнено ли сопоставление успешно и, в этом случае, какие группы захвата в регулярном выражении были определены.

Функции, принимающие объект `match_results`, указывают в своих членах, выполнено ли сопоставление успешно и, в этом случае, какие группы захвата в регулярном выражении были определены.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_match.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

using namespace std;

int main()
{
    // (1) with char*
    // Note how const char* requires cmatch and regex
    const char *first = "abc";
    const char *last = first + strlen(first);
    cmatch narrowMatch;
    regex rx("a(b)c");

    bool found = regex_match(first, last, narrowMatch, rx);
    if (found)
        wcout << L"Regex found in abc" << endl;

    // (2) with std::wstring
    // Note how wstring requires wsmatch and wregex.
    // Note use of const iterators cbegin() and cend().
    wstring target(L"Hello");
    wsmatch wideMatch;
    wregex wrx(L"He(l+)o");

    if (regex_match(target.cbegin(), target.cend(), wideMatch, wrx))
        wcout << L"The matching text is:" << wideMatch.str() << endl;

    // (3) with std::string
    string target2("Drizzle");
    regex rx2(R"(D\w+e)"); // no double backslashes with raw string literal

    found = regex_match(target2.cbegin(), target2.cend(), rx2);
    if (found)
        wcout << L"Regex found in Drizzle" << endl;

    // (4) with wchar_t*
    const wchar_t* target3 = L"2014-04-02";
    wcmatch wideMatch2;

    // LR"(...)" is a  raw wide-string literal. Open and close parens
    // are delimiters, not string elements.
    wregex wrx2(LR"(\d{4}(-|/)\d{2}(-|/)\d{2})");
    if (regex_match(target3, wideMatch2, wrx2))
    {
        wcout << L"Matching text: " << wideMatch2.str() << endl;
    }

     return 0;
}
```

```Output
Regex found in abc
The matching text is: Hello
Regex found in Drizzle
The matching text is: 2014-04-02
```

## <a name="regex_replace"></a><a name="regex_replace"></a>regex_replace

Заменяет соответствующие регулярные выражения.

```cpp
template <class OutIt, class BidIt, class RXtraits, class Alloc, class Elem>
OutIt regex_replace(
    OutIt out,
    BidIt first,
    BidIt last,
    const basic_regex<Elem, RXtraits, Alloc>& re,
    const basic_string<Elem>& fmt,
    match_flag_type flags = match_default);

template <class RXtraits, class Alloc, class Elem>
basic_string<Elem> regex_replace(
    const basic_string<Elem>& str,
    const basic_regex<Elem, RXtraits, Alloc>& re,
    const basic_string<Elem>& fmt,
    match_flag_type flags = match_default);
```

### <a name="parameters"></a>Параметры

*OutIt*\
Тип итератора для замен.

*BidIt*\
Тип итератора для подстрок соответствия.

*RXtraits*\
Класс характеристик для элементов.

*Alloc*\
Класс распределителя регулярного выражения.

*Elem*\
Тип элементов для обеспечения соответствия.

*Флаги*\
Флаги для соответствий.

*Первый*\
Начало последовательности для сопоставления.

*Fmt*\
Формат для замен.

*Последний*\
Конец последовательности для сопоставления.

*из*\
Итератор вывода.

*Повторно*\
Регулярное выражение для сопоставления.

*Ул*\
Сопоставляемая строка.

### <a name="remarks"></a>Remarks

Первая функция строит [regex_iterator Class](../standard-library/regex-iterator-class.md) объект `iter(first, last, re, flags)` regex_iterator класса и использует его `[first, last)` для разделения его `T0 M0 T1 M1...TN-1 MN-1 TN`вхоложства на ряд последовательность, где `Mn` находится n-й матч, обнаруженный итератором. Если совпадения не найдены, `T0` — это весь входной диапазон, а `N` равно нулю. Если `(flags & format_first_only) != 0`, используется только первое соответствие, `T1` — это весь входной текст, который следует за соответствием, а `N` равно 1. Для `i` каждого в `[0, N)`ряде, если `(flags & format_no_copy) == 0` оно скопирует текст в ряде `Ti` к итератору *вне.* Затем он `m.format(out, fmt, flags)`вызывает, `m` `match_results` где объект возвращается объектом `iter` итератора для последовательность. `Mi` Наконец, `(flags & format_no_copy) == 0` если он копирует `TN` текст в диапазоне к итератору *из*. Функция *возвращается*.

Вторая функция создает локальную переменную `result` типа `basic_string<charT>` и вызывает `regex_replace(back_inserter(result), str.begin(), str.end(), re, fmt, flags)`. Он возвращает `result`.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_replace.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    char buf[20];
    const char *first = "axayaz";
    const char *last = first + strlen(first);
    std::regex rx("a");
    std::string fmt("A");
    std::regex_constants::match_flag_type fonly =
        std::regex_constants::format_first_only;

    *std::regex_replace(&buf[0], first, last, rx, fmt) = '\0';
    std::cout << "replacement == " << &buf[0] << std::endl;

    *std::regex_replace(&buf[0], first, last, rx, fmt, fonly) = '\0';
    std::cout << "replacement == " << &buf[0] << std::endl;

    std::string str("adaeaf");
    std::cout << "replacement == "
        << std::regex_replace(str, rx, fmt) << std::endl;

    std::cout << "replacement == "
        << std::regex_replace(str, rx, fmt, fonly) << std::endl;

    return (0);
}
```

```Output
replacement == AxAyAz
replacement == Axayaz
replacement == AdAeAf
replacement == Adaeaf
```

## <a name="regex_search"></a><a name="regex_search"></a>regex_search

Поиск соответствия регулярному выражению.

```cpp
template <class BidIt, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    BidIt first,
    Bidit last,
    match_results<BidIt, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class BidIt, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    BidIt first,
    Bidit last,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class Elem, class Alloc, class RXtraits, class Alloc2>
bool regex_search(
    const Elem* ptr,
    match_results<const Elem*, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class Elem, class RXtraits, class Alloc2>
bool regex_search(
    const Elem* ptr,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class IOtraits, class IOalloc, class Alloc, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    match_results<typename basic_string<Elem, IOtraits, IOalloc>::const_iterator, Alloc>& match,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);

template <class IOtraits, class IOalloc, class Elem, class RXtraits, class Alloc2>
bool regex_search(
    const basic_string<Elem, IOtraits, IOalloc>& str,
    const basic_regex<Elem, RXtraits, Alloc2>& re,
    match_flag_type flags = match_default);
```

### <a name="parameters"></a>Параметры

*BidIt*\
Тип итератора для подстрок соответствия.

*Alloc*\
Класс распределителя результатов соответствия.

*Elem*\
Тип элементов для обеспечения соответствия.

*RXtraits*\
Класс характеристик для элементов.

*Аллок2*\
Класс распределителя регулярного выражения.

*Иотраиты*\
Класс характеристик строки.

*IOalloc*\
Класс распределителя строк.

*Флаги*\
Флаги для соответствий.

*Первый*\
Начало последовательности для сопоставления.

*Последний*\
Конец последовательности для сопоставления.

*Матч*\
Результаты сопоставления.

*Ptr*\
Указатель на начало последовательности для сопоставления.

*Повторно*\
Регулярное выражение для сопоставления.

*Ул*\
Сопоставляемая строка.

### <a name="remarks"></a>Remarks

Каждая функция шаблона возвращается верно только в том случае, если поиск его регулярного аргумента выражения *повторно* в своей последовательности работы удается. Функции, принимающие объект `match_results`, указывают в своих членах успешность выполнения поиска и, в этом случае, какие группы захвата в были распознаны в регулярном выражении.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_search.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    const char *first = "abcd";
    const char *last = first + strlen(first);
    std::cmatch mr;
    std::regex rx("abc");
    std::regex_constants::match_flag_type fl =
        std::regex_constants::match_default;

    std::cout << "search(f, f+1, \"abc\") == " << std::boolalpha
        << regex_search(first, first + 1, rx, fl) << std::endl;

    std::cout << "search(f, l, \"abc\") == " << std::boolalpha
        << regex_search(first, last, mr, rx) << std::endl;
    std::cout << "  matched: \"" << mr.str() << "\"" << std::endl;

    std::cout << "search(\"a\", \"abc\") == " << std::boolalpha
        << regex_search("a", rx) << std::endl;

    std::cout << "search(\"xabcd\", \"abc\") == " << std::boolalpha
        << regex_search("xabcd", mr, rx) << std::endl;
    std::cout << "  matched: \"" << mr.str() << "\"" << std::endl;

    std::cout << "search(string, \"abc\") == " << std::boolalpha
        << regex_search(std::string("a"), rx) << std::endl;

    std::string str("abcabc");
    std::match_results<std::string::const_iterator> mr2;
    std::cout << "search(string, \"abc\") == " << std::boolalpha
        << regex_search(str, mr2, rx) << std::endl;
    std::cout << "  matched: \"" << mr2.str() << "\"" << std::endl;

    return (0);
}
```

```Output
search(f, f+1, "abc") == false
search(f, l, "abc") == true
  matched: "abc"
search("a", "abc") == false
search("xabcd", "abc") == true
  matched: "abc"
search(string, "abc") == false
search(string, "abc") == true
  matched: "abc"
```

## <a name="swap"></a><a name="swap"></a>Своп

Свопы `basic_regex` `match_results` два или объекты.

```cpp
template <class Elem, class RXtraits>
void swap(
    basic_regex<Elem, RXtraits, Alloc>& left,
    basic_regex<Elem, RXtraits>& right) noexcept;

template <class Elem, class IOtraits, class BidIt, class Alloc>
void swap(
    match_results<BidIt, Alloc>& left,
    match_results<BidIt, Alloc>& right) noexcept;
```

### <a name="parameters"></a>Параметры

*Elem*\
Тип элементов для обеспечения соответствия.

*RXtraits*\
Класс характеристик для элементов.

### <a name="remarks"></a>Remarks

Функции-шаблоны обменивают содержимое своих аргументов в постоянном времени и не создают исключений.

### <a name="example"></a>Пример

```cpp
// std__regex__swap.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

int main()
{
    std::regex rx0("c(a*)|(b)");
    std::regex rx1;
    std::cmatch mr0;
    std::cmatch mr1;

    swap(rx0, rx1);
    std::regex_search("xcaaay", mr1, rx1);
    swap(mr0, mr1);

    std::csub_match sub = mr0[1];
    std::cout << "matched == " << std::boolalpha
        << sub.matched << std::endl;
    std::cout << "length == " << sub.length() << std::endl;
    std::cout << "string == " << sub << std::endl;

    return (0);
}
```

```Output
matched == true
length == 3
string == aaa
```

## <a name="see-also"></a>См. также раздел

[\<regex>](../standard-library/regex.md)\
[класс regex_constants](../standard-library/regex-constants-class.md)\
[regex_error класс](../standard-library/regex-error-class.md)\
[класс regex_iterator](../standard-library/regex-iterator-class.md)\
[\<операторы regex>](../standard-library/regex-operators.md)\
[класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)\
[класс regex_traits](../standard-library/regex-traits-class.md)\
[\<regex> typedefs](../standard-library/regex-typedefs.md)
