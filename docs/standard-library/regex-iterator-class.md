---
title: Класс regex_iterator
ms.date: 09/10/2018
f1_keywords:
- regex/std::regex_iterator
- regex/std::regex_iterator::operator==
- regex/std::regex_iterator::operator!=
- regex/std::regex_iterator::operator*
- regex/std::regex_iterator::operator->
- regex/std::regex_iterator::operator++
helpviewer_keywords:
- std::regex_iterator
- std::regex_iterator::operator==
- std::regex_iterator::operator!=
- std::regex_iterator::operator*
- std::regex_iterator::operator->
- std::regex_iterator::operator++
ms.assetid: 0cfd8fd0-5a95-4f3c-bf8e-6ef028c423d3
ms.openlocfilehash: 937c217cdef6895aaa3adb1499f1fde8f67fd513
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482632"
---
# <a name="regexiterator-class"></a>Класс regex_iterator

Класс итератора для соответствий.

## <a name="syntax"></a>Синтаксис

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_iterator
```

## <a name="parameters"></a>Параметры

*BidIt*<br/>
Тип итератора для подстрок соответствия.

*Elem*<br/>
Тип элементов для обеспечения соответствия.

*RXtraits*<br/>
Класс характеристик для элементов.

## <a name="remarks"></a>Примечания

Класс шаблона описывает объект постоянного прямого итератора. Он извлекает объекты типа `match_results<BidIt>` , несколько раз применяя объект регулярного выражения `*pregex` к последовательности символов, определенной диапазоном итератора `[begin, end)`.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[regex_iterator](#regex_iterator)|Формирует итератор.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[difference_type](#difference_type)|Тип разницы итератора.|
|[iterator_category](#iterator_category)|Тип категории итератора.|
|[pointer](#pointer)|Тип указателя на совпадение.|
|[reference](#reference)|Тип ссылки на соответствие.|
|[regex_type](#regex_type)|Тип регулярного выражения для сопоставления.|
|[value_type](#value_type)|Тип соответствия.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[operator!=](#op_neq)|Сравнивает итераторы на неравенство.|
|[оператор*](#op_star)|Обращается к заданному соответствию.|
|[оператор++](#op_add_add)|Увеличивает значение итератора.|
|[оператор=](#op_eq)|Сравнивает итераторы на равенство.|
|[оператор>](#op_arrow)|Обращается к заданному соответствию.|

## <a name="requirements"></a>Требования

**Заголовок:** \<regex>

**Пространство имен:** std

## <a name="examples"></a>Примеры

Примеры регулярных выражений см. в следующих разделах:

- [regex_match](../standard-library/regex-functions.md#regex_match)

- [regex_replace](../standard-library/regex-functions.md#regex_replace)

- [regex_search](../standard-library/regex-functions.md#regex_search)

- [swap](../standard-library/regex-functions.md#swap)

```cpp
// std__regex__regex_iterator.cpp
// compile with: /EHsc
#include <regex>
#include <iostream>

typedef std::regex_iterator<const char *> Myiter;
int main()
    {
    const char *pat = "axayaz";
    Myiter::regex_type rx("a");
    Myiter next(pat, pat + strlen(pat), rx);
    Myiter end;

    for (; next != end; ++next)
        std::cout << "match == " << next->str() << std::endl;

// other members
    Myiter it1(pat, pat + strlen(pat), rx);
    Myiter it2(it1);
    next = it1;

    Myiter::iterator_category cat = std::forward_iterator_tag();
    Myiter::difference_type dif = -3;
    Myiter::value_type mr = *it1;
    Myiter::reference ref = mr;
    Myiter::pointer ptr = &ref;

    dif = dif; // to quiet "unused" warnings
    ptr = ptr;

    return (0);
    }
```

```Output
match == a
match == a
match == a
```

## <a name="difference_type"></a>  regex_iterator::difference_type

Тип разницы итератора.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом `std::ptrdiff_t`.

## <a name="iterator_category"></a>  regex_iterator::iterator_category

Тип категории итератора.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>Примечания

Тип является синонимом `std::forward_iterator_tag`.

## <a name="op_neq"></a>  regex_iterator::operator!=

Сравнивает итераторы на неравенство.

```cpp
bool operator!=(const regex_iterator& right);
```

### <a name="parameters"></a>Параметры

*right*<br/>
Итератор для сравнения.

### <a name="remarks"></a>Примечания

Функция-член возвращает значение `!(*this == right)`.

## <a name="op_star"></a>  regex_iterator::operator*

Обращается к заданному соответствию.

```cpp
const match_results<BidIt>& operator*();
```

### <a name="remarks"></a>Примечания

Эта функция-член возвращает хранимое значение `match`.

## <a name="op_add_add"></a>  regex_iterator::operator++

Увеличивает значение итератора.

```cpp
regex_iterator& operator++();
regex_iterator& operator++(int);
```

### <a name="remarks"></a>Примечания

Если текущее совпадение не содержит символы, первый оператор вызывает `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail | regex_constants::match_not_null)`; в противном случае он выполняет переход к сохраненному значению `begin` для указания на первый символ после текущего совпадения, затем вызывает `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail)`. В любом случае, если поиск заканчивается неудачно, оператор задает для объекта итератор конца последовательности. Оператор возвращает объект.

Второй оператор создает копию объекта, увеличивает объект, а затем возвращает копию.

## <a name="op_eq"></a>  regex_iterator::operator=

Сравнивает итераторы на равенство.

```cpp
bool operator==(const regex_iterator& right);
```

### <a name="parameters"></a>Параметры

*right*<br/>
Итератор для сравнения.

### <a name="remarks"></a>Примечания

Функция-член возвращает значение true, если `*this` и *правой* как итераторы конец последовательности, или если ни один не итератор конец последовательности и `begin == right.begin`, `end == right.end`, `pregex == right.pregex`, и `flags == right.flags`. В противном случае возвращается значение false.

## <a name="op_arrow"></a>  regex_iterator::operator-&gt;

Обращается к заданному соответствию.

```cpp
const match_results<BidIt> * operator->();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает адрес сохраненного значения `match`.

## <a name="pointer"></a>  regex_iterator::pointer

Тип указателя на совпадение.

```cpp
typedef match_results<BidIt> *pointer;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для `match_results<BidIt>*`, где `BidIt` — параметр шаблона.

## <a name="reference"></a>  regex_iterator::reference

Тип ссылки на соответствие.

```cpp
typedef match_results<BidIt>& reference;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для `match_results<BidIt>&`, где `BidIt` — параметр шаблона.

## <a name="regex_iterator"></a>  regex_iterator::regex_iterator

Формирует итератор.

```cpp
regex_iterator();

regex_iterator(BidIt first,
    BidIt last,
    const regex_type& re,
    regex_constants::match_flag_type f = regex_constants::match_default);
```

### <a name="parameters"></a>Параметры

*Первый*<br/>
Начало последовательности для сопоставления.

*последний*<br/>
Конец последовательности для сопоставления.

*RE*<br/>
Регулярное выражение для соответствий.

*f*<br/>
Флаги для соответствий.

### <a name="remarks"></a>Примечания

Первый конструктор создает итератор конца последовательности. Второй конструктор инициализирует сохраненное значение `begin` с *первый*, сохраненное значение `end` с *последнего*, сохраненное значение `pregex` с `&re`и сохраненное значение `flags` с *f*. Затем он вызывает `regex_search(begin, end, match, *pregex, flags)`. Если поиск заканчивается неудачно, конструктор задает для объекта итератор конца последовательности.

## <a name="regex_type"></a>  regex_iterator::regex_type

Тип регулярного выражения для сопоставления.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>Примечания

Typedef является синонимом `basic_regex<Elem, RXtraits>`.

## <a name="value_type"></a>  regex_iterator::value_type

Тип соответствия.

```cpp
typedef match_results<BidIt> value_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для `match_results<BidIt>`, где `BidIt` — параметр шаблона.

## <a name="see-also"></a>См. также

[\<regex>](../standard-library/regex.md)<br/>
[Класс regex_constants](../standard-library/regex-constants-class.md)<br/>
[Класс regex_error](../standard-library/regex-error-class.md)<br/>
[Функции \<regex>](../standard-library/regex-functions.md)<br/>
[Класс regex_iterator](../standard-library/regex-iterator-class.md)<br/>
[Операторы \<regex>](../standard-library/regex-operators.md)<br/>
[Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)<br/>
[Класс regex_traits](../standard-library/regex-traits-class.md)<br/>
[Определения типов \<regex>](../standard-library/regex-typedefs.md)<br/>
