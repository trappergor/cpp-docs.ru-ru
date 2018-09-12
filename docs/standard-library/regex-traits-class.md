---
title: Класс regex_traits | Документы Майкрософт
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- regex/std::regex_traits
- regex/std::regex_traits::char_type
- regex/std::regex_traits::size_type
- regex/std::regex_traits::string_type
- regex/std::regex_traits::locale_type
- regex/std::regex_traits::char_class_type
- regex/std::regex_traits::length
- regex/std::regex_traits::translate
- regex/std::regex_traits::translate_nocase
- regex/std::regex_traits::transform
- regex/std::regex_traits::transform_primary
- regex/std::regex_traits::lookup_classname
- regex/std::regex_traits::lookup_collatename
- regex/std::regex_traits::isctype
- regex/std::regex_traits::value
- regex/std::regex_traits::imbue
- regex/std::regex_traits::getloc
dev_langs:
- C++
helpviewer_keywords:
- std::regex_traits [C++]
- std::regex_traits [C++], char_type
- std::regex_traits [C++], size_type
- std::regex_traits [C++], string_type
- std::regex_traits [C++], locale_type
- std::regex_traits [C++], char_class_type
- std::regex_traits [C++], length
- std::regex_traits [C++], translate
- std::regex_traits [C++], translate_nocase
- std::regex_traits [C++], transform
- std::regex_traits [C++], transform_primary
- std::regex_traits [C++], lookup_classname
- std::regex_traits [C++], lookup_collatename
- std::regex_traits [C++], isctype
- std::regex_traits [C++], value
- std::regex_traits [C++], imbue
- std::regex_traits [C++], getloc
ms.assetid: bc5a5eed-32fc-4eb7-913d-71c42e729e81
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 747737125a54ab67f042d286074414d8b4a1e878
ms.sourcegitcommit: fb9448eb96c6351a77df04af16ec5c0fb9457d9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691579"
---
# <a name="regextraits-class"></a>Класс regex_traits

Описывает характеристики элементов для сопоставления.

## <a name="syntax"></a>Синтаксис

```cpp
template<class Elem>
class regex_traits 
```

## <a name="parameters"></a>Параметры

*Elem*<br/>
Тип элемента символа для описания.

## <a name="remarks"></a>Примечания

Класс шаблона описывает различные характеристики регулярного выражения для типа *Elem*. Класс шаблона [класс basic_regex](../standard-library/basic-regex-class.md) использует эти сведения для управления элементами типа *Elem*.

Каждый объект `regex_traits` содержит объект типа `regex_traits::locale` , используемый некоторыми из его функций-членов. Языковой стандарт по умолчанию является копией `regex_traits::locale()`. Функция-член `imbue` заменяет объект языкового стандарта, а функция-член `getloc` возвращает копию объекта языкового стандарта.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[regex_traits](#regex_traits)|Создает объект.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_class_type](#char_class_type)|Тип обозначений класса символов.|
|[char_type](#char_type)|Тип элемента.|
|[locale_type](#locale_type)|Тип сохраненного объекта языкового стандарта.|
|[size_type](#size_type)|Тип длины последовательности.|
|[string_type](#string_type)|Тип строки элементов.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[getloc](#getloc)|Возвращает сохраненный объект языкового стандарта.|
|[imbue](#imbue)|Изменяет сохраненный объект языкового стандарта.|
|[isctype](#isctype)|Проверяет членство в классе.|
|[length](#length)|Возвращает длину последовательности, завершающаяся символом null.|
|[lookup_classname](#lookup_classname)|Сопоставляет последовательность с классом символов.|
|[lookup_collatename](#lookup_collatename)|Сопоставляет последовательность с элементом упорядочивания.|
|[transform](#transform)|Преобразует в эквивалентную упорядоченную последовательность.|
|[transform_primary](#transform_primary)|Преобразует в эквивалентную упорядоченную последовательность без учета регистра.|
|[Перевести](#translate)|Преобразует в эквивалентный соответствующий элемент.|
|[translate_nocase](#translate_nocase)|Преобразует в эквивалентный соответствующий элемент без учета регистра.|
|[value](#value)|Преобразует элемент в цифровое значение.|

## <a name="requirements"></a>Требования

**Заголовок:** \<regex>

**Пространство имен:** std

## <a name="example"></a>Пример

```cpp
// std__regex__regex_traits.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_traits<char> Mytr;
int main()
    {
    Mytr tr;

    Mytr::char_type ch = tr.translate('a');
    std::cout << "translate('a') == 'a' == " << std::boolalpha
        << (ch == 'a') << std::endl;

    std::cout << "nocase 'a' == 'A' == " << std::boolalpha
        << (tr.translate_nocase('a') == tr.translate_nocase('A'))
        << std::endl;

    const char *lbegin = "abc";
    const char *lend = lbegin + strlen(lbegin);
    Mytr::size_type size = tr.length(lbegin);
    std::cout << "length(\"abc\") == " << size <<std::endl;

    Mytr::string_type str = tr.transform(lbegin, lend);
    std::cout << "transform(\"abc\") < \"abc\" == " << std::boolalpha
        << (str < "abc") << std::endl;

    const char *ubegin = "ABC";
    const char *uend = ubegin + strlen(ubegin);
    std::cout << "primary \"ABC\" < \"abc\" == " << std::boolalpha
        << (tr.transform_primary(ubegin, uend) <
            tr.transform_primary(lbegin, lend))
        << std::endl;

    const char *dig = "digit";
    Mytr::char_class_type cl = tr.lookup_classname(dig, dig + 5);
    std::cout << "class digit == d == " << std::boolalpha
        << (cl == tr.lookup_classname(dig, dig + 1))
        << std::endl;

    std::cout << "'3' is digit == " <<std::boolalpha
        << tr.isctype('3', tr.lookup_classname(dig, dig + 5))
        << std::endl;

    std::cout << "hex C == " << tr.value('C', 16) << std::endl;

// other members
    str = tr.lookup_collatename(dig, dig + 5);

    Mytr::locale_type loc = tr.getloc();
    tr.imbue(loc);

    return (0);
    }
```

```Output
translate('a') == 'a' == true
nocase 'a' == 'A' == true
length("abc") == 3
transform("abc") < "abc" == false
primary "ABC" < "abc" == false
class digit == d == true
'3' is digit == true
hex C == 12
```

## <a name="char_class_type"></a>  regex_traits::char_class_type

Тип обозначений класса символов.

```cpp
typedef T8 char_class_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом незаданного типа, который обозначает классы символов. Значения этого типа могут быть объединены с помощью оператора `|` для обозначения классов символов, которые представляют собой объединение классов, указанных операндами.

## <a name="char_type"></a>  regex_traits::char_type

Тип элемента.

```cpp
typedef Elem char_type;
```

### <a name="remarks"></a>Примечания

Определение типа является синонимом параметра шаблона `Elem`.

## <a name="getloc"></a>  regex_traits::getloc

Возвращает сохраненный объект языкового стандарта.

```cpp
locale_type getloc() const;
```

### <a name="remarks"></a>Примечания

Эта функция-член возвращает хранимый объект `locale` .

## <a name="imbue"></a>  regex_traits::imbue

Изменяет сохраненный объект языкового стандарта.

```cpp
locale_type imbue(locale_type loc);
```

### <a name="parameters"></a>Параметры

*Loc*<br/>
Объект языкового стандарта, который необходимо сохранить.

### <a name="remarks"></a>Примечания

Функция-член копирует *loc* сохраненному `locale` и возвращает копию предыдущего значения сохраненного `locale` объекта.

## <a name="isctype"></a>  regex_traits::isctype

Проверяет членство в классе.

```cpp
bool isctype(char_type ch, char_class_type cls) const;
```

### <a name="parameters"></a>Параметры

*ch*<br/>
Элемент для проверки.

*CLS*<br/>
Классы для проверки.

### <a name="remarks"></a>Примечания

Функция-член возвращает значение true только в том случае, если символ *ch* находится в классе символов, указанном *cls*.

## <a name="length"></a>  regex_traits::length

Возвращает длину последовательности, завершающаяся символом null.

```cpp
static size_type length(const char_type *str);
```

### <a name="parameters"></a>Параметры

*str*<br/>

Завершающаяся нулем последовательность.

### <a name="remarks"></a>Примечания

Статическая функция-член возвращает значение `std::char_traits<char_type>::length(str)`.

## <a name="locale_type"></a>  regex_traits::locale_type

Тип сохраненного объекта языкового стандарта.

```cpp
typedef T7 locale_type;
```

### <a name="remarks"></a>Примечания

Определение типа является синонимом типа, который инкапсулирует языковые стандарты. В специализациях `regex_traits<char>` и `regex_traits<wchar_t>` он является синонимом `std::locale`.

## <a name="lookup_classname"></a>  regex_traits::lookup_classname

Сопоставляет последовательность с классом символов.

```cpp
template <class FwdIt>
char_class_type lookup_classname(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Параметры

*Первый*<br/>
Начало искомой последовательности.

*последний*<br/>
Конец искомой последовательности.

### <a name="remarks"></a>Примечания

Функция-член возвращает значение, которое определяет класс символов с именем, образуемым последовательностью символов, на которую указывают аргументы. Значение не зависит от регистра символов в последовательности.

Специализация `regex_traits<char>` распознает имена `"d"`, `"s"`, `"w"`, `"alnum"`, `"alpha"`, `"blank"`, `"cntrl"`, `"digit"`, `"graph"`, `"lower"`, `"print"`, `"punct"`, `"space"`, `"upper"` и `"xdigit"`, все без учета регистра.

Специализация `regex_traits<wchar_t>` распознает имена `L"d"`, `L"s"`, `L"w"`, `L"alnum"`, `L"alpha"`, `L"blank"`, `L"cntrl"`, `L"digit"`, `L"graph"`, `L"lower"`, `L"print"`, `L"punct"`, `L"space"`, `L"upper"` и `L"xdigit"`, все без учета регистра.

## <a name="lookup_collatename"></a>  regex_traits::lookup_collatename

Сопоставляет последовательность с элементом упорядочивания.

```cpp
template <class FwdIt>
string_type lookup_collatename(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Параметры

*Первый*<br/>
Начало искомой последовательности.

*последний*<br/>
Конец искомой последовательности.

### <a name="remarks"></a>Примечания

Функция-член возвращает строковый объект, содержащий элемент упорядочивания, соответствующий последовательности `[first, last)`, или пустую строку, если последовательность не является допустимым элементом упорядочивания.

## <a name="regex_traits"></a>  regex_traits::regex_traits

Создает объект.

```cpp
regex_traits();
```

### <a name="remarks"></a>Примечания

Конструктор создает объект, хранимый объект `locale` которого инициализируется с  языковым стандартом по умолчанию.

## <a name="size_type"></a>  regex_traits::size_type

Тип длины последовательности.

```cpp
typedef T6 size_type;
```

### <a name="remarks"></a>Примечания

Typedef выступает синонимом для целочисленного типа без знака. В специализациях `regex_traits<char>` и `regex_traits<wchar_t>` он является синонимом `std::size_t`.

Typedef является синонимом `std::size_t`.

## <a name="string_type"></a>  regex_traits::string_type

Тип строки элементов.

```cpp
typedef basic_string<Elem> string_type;
```

### <a name="remarks"></a>Примечания

Typedef является синонимом `basic_string<Elem>`.

## <a name="transform"></a>  regex_traits::transform

Преобразует в эквивалентную упорядоченную последовательность.

```cpp
template <class FwdIt>
string_type transform(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Параметры

*Первый*<br/>
Начало преобразуемой последовательности.

*последний*<br/>
Конец преобразуемой последовательности.

### <a name="remarks"></a>Примечания

Функция-член возвращает строку, которая создается с помощью правила преобразования, зависящего от сохраненного объекта `locale` . Для двух последовательностей символов, указанных диапазонами итератора `[first1, last1)` и `[first2, last2)`, значение `transform(first1, last1) < transform(first2, last2)` , если последовательность символов, указанная диапазоном итератора `[first1, last1)` , предшествует последовательности символов, указанной диапазоном итератора `[first2, last2)`.

## <a name="transform_primary"></a>  regex_traits::transform_primary

Преобразует в эквивалентную упорядоченную последовательность без учета регистра.

```cpp
template <class FwdIt>
string_type transform_primary(FwdIt first, FwdIt last) const;
```

### <a name="parameters"></a>Параметры

*Первый*<br/>
Начало преобразуемой последовательности.

*последний*<br/>
Конец преобразуемой последовательности.

### <a name="remarks"></a>Примечания

Функция-член возвращает строку, которая создается с помощью правила преобразования, зависящего от сохраненного объекта `locale` . Для двух последовательностей символов, указанных диапазонами итератора `[first1, last1)` и `[first2, last2)`, выражение `transform_primary(first1, last1) < transform_primary(first2, last2)` , если последовательность символов, указанная диапазоном итератора `[first1, last1)` , выполняет сортировку до последовательности символов, указанной диапазоном итератора `[first2, last2)` , без учета регистра и диакритических знаков.

## <a name="translate"></a>  regex_traits::translate

Преобразует в эквивалентный соответствующий элемент.

```cpp
char_type translate(char_type ch) const;
```

### <a name="parameters"></a>Параметры

*ch*<br/>
Преобразуемый элемент.

### <a name="remarks"></a>Примечания

Функция-член возвращает символ, который создается с помощью правила преобразования, зависящего от сохраненного объекта `locale` . Для двух объектов `char_type` , `ch1` и `ch2`, значение `translate(ch1) == translate(ch2)` , только если `ch1` и `ch2` должны совпадать, когда один объект возникает в определении регулярного выражения, а второй — в соответствующей позиции в целевой последовательности для сопоставления, зависящего от языкового стандарта.

## <a name="translate_nocase"></a>  regex_traits::translate_nocase

Преобразует в эквивалентный соответствующий элемент без учета регистра.

```cpp
char_type translate_nocase(char_type ch) const;
```

### <a name="parameters"></a>Параметры

*ch*<br/>
Преобразуемый элемент.

### <a name="remarks"></a>Примечания

Функция-член возвращает символ, который создается с помощью правила преобразования, зависящего от сохраненного объекта `locale` . Для двух объектов `char_type` , `ch1` и `ch2`, значение `translate_nocase(ch1) == translate_nocase(ch2)` , только если `ch1` и `ch2` должны совпадать, когда один объект возникает в определении регулярного выражения, а второй — в соответствующей позиции в целевой последовательности для сопоставления, не учитывающего регистр.

## <a name="value"></a>  regex_traits::value

Преобразует элемент в цифровое значение.

```cpp
int value(Elem ch, int radix) const;
```

### <a name="parameters"></a>Параметры

*ch*<br/>
Преобразуемый элемент.

*radix*<br/>
Используемое арифметическое основание.

### <a name="remarks"></a>Примечания

Функция-член возвращает значение, представленное символом *ch* в базовом *основание системы счисления*, или -1, если *ch* не является допустимой цифрой в базовом *основание системы счисления*. Функция будет вызываться только с *основание системы счисления* аргумент 8, 10 или 16.

## <a name="see-also"></a>См. также

[\<regex>](../standard-library/regex.md)<br/>
[Класс regex_constants](../standard-library/regex-constants-class.md)<br/>
[Класс regex_error](../standard-library/regex-error-class.md)<br/>
[Функции \<regex>](../standard-library/regex-functions.md)<br/>
[Класс regex_iterator](../standard-library/regex-iterator-class.md)<br/>
[Операторы \<regex>](../standard-library/regex-operators.md)<br/>
[Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)<br/>
[Определения типов \<regex>](../standard-library/regex-typedefs.md)<br/>
[regex_traits\<char > класс](../standard-library/regex-traits-char-class.md)<br/>
Класс [regex_traits\<wchar_t>](../standard-library/regex-traits-wchar-t-class.md)<br/>
