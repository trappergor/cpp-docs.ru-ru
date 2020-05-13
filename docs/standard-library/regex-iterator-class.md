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
ms.openlocfilehash: 6bc57d6815fa6f30e26b22e9b7ab758a1ac20e16
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374558"
---
# <a name="regex_iterator-class"></a>Класс regex_iterator

Класс итератора для соответствий.

## <a name="syntax"></a>Синтаксис

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_iterator
```

## <a name="parameters"></a>Параметры

*BidIt*\
Тип итератора для подстрок соответствия.

*Elem*\
Тип элементов для обеспечения соответствия.

*RXtraits*\
Класс характеристик для элементов.

## <a name="remarks"></a>Remarks

Шаблон класса описывает постоянный объект итератора вперед. Он извлекает объекты типа `match_results<BidIt>` , несколько раз применяя объект регулярного выражения `*pregex` к последовательности символов, определенной диапазоном итератора `[begin, end)`.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[regex_iterator](#regex_iterator)|Формирует итератор.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[difference_type](#difference_type)|Тип разницы итератора.|
|[iterator_category](#iterator_category)|Тип категории итератора.|
|[указатель](#pointer)|Тип указателя на совпадение.|
|[Ссылки](#reference)|Тип ссылки на соответствие.|
|[regex_type](#regex_type)|Тип регулярного выражения для сопоставления.|
|[Value_type](#value_type)|Тип соответствия.|

### <a name="operators"></a>Операторы

|Оператор|Описание|
|-|-|
|[оператора!](#op_neq)|Сравнивает итераторы на неравенство.|
|[оператор](#op_star)|Обращается к заданному соответствию.|
|[оператор](#op_add_add)|Увеличивает значение итератора.|
|[оператора](#op_eq)|Сравнивает итераторы на равенство.|
|[оператор->](#op_arrow)|Обращается к заданному соответствию.|

## <a name="requirements"></a>Требования

**Заголовок:** \<regex>

**Пространство имен:** std

## <a name="examples"></a>Примеры

Примеры регулярных выражений см. в следующих разделах:

- [regex_match](../standard-library/regex-functions.md#regex_match)

- [regex_replace](../standard-library/regex-functions.md#regex_replace)

- [regex_search](../standard-library/regex-functions.md#regex_search)

- [Своп](../standard-library/regex-functions.md#swap)

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

## <a name="regex_iteratordifference_type"></a><a name="difference_type"></a>regex_iterator::difference

Тип разницы итератора.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Remarks

Тип является синонимом `std::ptrdiff_t`.

## <a name="regex_iteratoriterator_category"></a><a name="iterator_category"></a>regex_iterator::iterator_category

Тип категории итератора.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>Remarks

Тип является синонимом `std::forward_iterator_tag`.

## <a name="regex_iteratoroperator"></a><a name="op_neq"></a>regex_iterator::оператор!

Сравнивает итераторы на неравенство.

```cpp
bool operator!=(const regex_iterator& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Итератор для сравнения.

### <a name="remarks"></a>Remarks

Функция-член возвращает значение `!(*this == right)`.

## <a name="regex_iteratoroperator"></a><a name="op_star"></a>regex_iterator::оператор

Обращается к заданному соответствию.

```cpp
const match_results<BidIt>& operator*();
```

### <a name="remarks"></a>Remarks

Эта функция-член возвращает хранимое значение `match`.

## <a name="regex_iteratoroperator"></a><a name="op_add_add"></a>regex_iterator::оператор

Увеличивает значение итератора.

```cpp
regex_iterator& operator++();
regex_iterator& operator++(int);
```

### <a name="remarks"></a>Remarks

Если текущее совпадение не содержит символы, первый оператор вызывает `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail | regex_constants::match_not_null)`; в противном случае он выполняет переход к сохраненному значению `begin` для указания на первый символ после текущего совпадения, затем вызывает `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail)`. В любом случае, если поиск заканчивается неудачно, оператор задает для объекта итератор конца последовательности. Оператор возвращает объект.

Второй оператор создает копию объекта, увеличивает объект, а затем возвращает копию.

## <a name="regex_iteratoroperator"></a><a name="op_eq"></a>regex_iterator:оператор

Сравнивает итераторы на равенство.

```cpp
bool operator==(const regex_iterator& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Итератор для сравнения.

### <a name="remarks"></a>Remarks

Функция члена возвращается `*this` верно, если и *справа* оба конца последовательности итераторов или, если `begin == right.begin`ни `end == right.end` `pregex == right.pregex`один `flags == right.flags`из конечных итераторов и , , и , и . В противном случае возвращается значение false.

## <a name="regex_iteratoroperator-gt"></a><a name="op_arrow"></a>regex_iterator::оператор-&gt;

Обращается к заданному соответствию.

```cpp
const match_results<BidIt> * operator->();
```

### <a name="remarks"></a>Remarks

Функция-член возвращает адрес сохраненного значения `match`.

## <a name="regex_iteratorpointer"></a><a name="pointer"></a>regex_iterator::pоинтер

Тип указателя на совпадение.

```cpp
typedef match_results<BidIt> *pointer;
```

### <a name="remarks"></a>Remarks

Этот тип является синонимом для `match_results<BidIt>*`, где `BidIt` — параметр шаблона.

## <a name="regex_iteratorreference"></a><a name="reference"></a>regex_iterator::ссылка

Тип ссылки на соответствие.

```cpp
typedef match_results<BidIt>& reference;
```

### <a name="remarks"></a>Remarks

Этот тип является синонимом для `match_results<BidIt>&`, где `BidIt` — параметр шаблона.

## <a name="regex_iteratorregex_iterator"></a><a name="regex_iterator"></a>regex_iterator::regex_iterator

Формирует итератор.

```cpp
regex_iterator();

regex_iterator(BidIt first,
    BidIt last,
    const regex_type& re,
    regex_constants::match_flag_type f = regex_constants::match_default);
```

### <a name="parameters"></a>Параметры

*Первый*\
Начало последовательности для сопоставления.

*Последний*\
Конец последовательности для сопоставления.

*Повторно*\
Регулярное выражение для соответствий.

*F*\
Флаги для соответствий.

### <a name="remarks"></a>Remarks

Первый конструктор создает итератор конца последовательности. Второй конструктор инициализирует `begin` сохраненное значение `end` с *первым,* сохраненное значение `flags` с *последним,* сохраненное значение `pregex` с, `&re`и сохраненное значение с *f*. Затем он вызывает `regex_search(begin, end, match, *pregex, flags)`. Если поиск заканчивается неудачно, конструктор задает для объекта итератор конца последовательности.

## <a name="regex_iteratorregex_type"></a><a name="regex_type"></a>regex_iterator::regex_type

Тип регулярного выражения для сопоставления.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>Remarks

Typedef является синонимом `basic_regex<Elem, RXtraits>`.

## <a name="regex_iteratorvalue_type"></a><a name="value_type"></a>regex_iterator::value_type

Тип соответствия.

```cpp
typedef match_results<BidIt> value_type;
```

### <a name="remarks"></a>Remarks

Этот тип является синонимом для `match_results<BidIt>`, где `BidIt` — параметр шаблона.

## <a name="see-also"></a>См. также раздел

[\<regex>](../standard-library/regex.md)\
[класс regex_constants](../standard-library/regex-constants-class.md)\
[regex_error класс](../standard-library/regex-error-class.md)\
[\<функции regex>](../standard-library/regex-functions.md)\
[класс regex_iterator](../standard-library/regex-iterator-class.md)\
[\<операторы regex>](../standard-library/regex-operators.md)\
[класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)\
[класс regex_traits](../standard-library/regex-traits-class.md)\
[\<regex> typedefs](../standard-library/regex-typedefs.md)
