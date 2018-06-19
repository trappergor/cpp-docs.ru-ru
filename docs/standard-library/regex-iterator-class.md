---
title: Класс regex_iterator | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- regex/std::regex_iterator
- regex/std::regex_iterator::operator==
- regex/std::regex_iterator::operator!=
- regex/std::regex_iterator::operator*
- regex/std::regex_iterator::operator->
- regex/std::regex_iterator::operator++
dev_langs:
- C++
helpviewer_keywords:
- std::regex_iterator
- std::regex_iterator::operator==
- std::regex_iterator::operator!=
- std::regex_iterator::operator*
- std::regex_iterator::operator->
- std::regex_iterator::operator++
ms.assetid: 0cfd8fd0-5a95-4f3c-bf8e-6ef028c423d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fffa778854519bff6f947aec779e36b77fd4e202
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861302"
---
# <a name="regexiterator-class"></a>Класс regex_iterator

Класс итератора для соответствий.

## <a name="syntax"></a>Синтаксис

```cpp
template<class BidIt,
   class Elem = typename std::iterator_traits<BidIt>::value_type,
   class RxTraits = regex_traits<Elem> >
class regex_iterator {
public:
   typedef basic_regex<Elem, RXtraits> regex_type;
   typedef match_results<BidIt> value_type;
   typedef std::forward_iterator_tag iterator_category;
   typedef std::ptrdiff_t difference_type;
   typedef const match_results<BidIt>* pointer;
   typedef const match_results<BidIt>& reference;

   regex_iterator();
   regex_iterator(
      BidIt first, BidIt last, const regex_type& re,
      regex_constants::match_flag_type f = regex_constants::match_default);

   bool operator==(const regex_iterator& right);
   bool operator!=(const regex_iterator& right);
   const match_results<BidIt>& operator*();
   const match_results<BidIt> * operator->();
   regex_iterator& operator++();
   regex_iterator& operator++(int);

private:
   BidIt begin; // exposition only
   BidIt end; // exposition only
   regex_type *pregex;     // exposition only
   regex_constants::match_flag_type flags; // exposition only
   match_results<BidIt> match; // exposition only
   };
```

### <a name="parameters"></a>Параметры

`BidIt` Тип итератора для подстрок соответствия.

`Elem` Тип элементов для обеспечения соответствия.

`RXtraits` Класс характеристик для элементов.

## <a name="remarks"></a>Примечания

Класс шаблона описывает объект постоянного прямого итератора. Он извлекает объекты типа `match_results<BidIt>` , несколько раз применяя объект регулярного выражения `*pregex` к последовательности символов, определенной диапазоном итератора `[begin, end)`.

## <a name="examples"></a>Примеры

Примеры регулярных выражений см. в следующих разделах:

- [regex_match](../standard-library/regex-functions.md#regex_match)

- [regex_replace](../standard-library/regex-functions.md#regex_replace)

- [regex_search](../standard-library/regex-functions.md#regex_search)

- [swap](../standard-library/regex-functions.md#swap)

## <a name="requirements"></a>Требования

**Заголовок:** \<regex>

**Пространство имен:** std

## <a name="difference_type"></a>  regex_iterator::difference_type

Тип разницы итератора.

```cpp
typedef std::ptrdiff_t difference_type;
```

### <a name="remarks"></a>Примечания

Тип является синонимом `std::ptrdiff_t`.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_iterator_difference_type.cpp
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

## <a name="iterator_category"></a>  regex_iterator::iterator_category

Тип категории итератора.

```cpp
typedef std::forward_iterator_tag iterator_category;
```

### <a name="remarks"></a>Примечания

Тип является синонимом `std::forward_iterator_tag`.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_iterator_iterator_category.cpp
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

## <a name="op_neq"></a>  regex_iterator::operator!=

Сравнивает итераторы на неравенство.

```cpp
bool operator!=(const regex_iterator& right);
```

### <a name="parameters"></a>Параметры

`right` Итератор для сравнения.

### <a name="remarks"></a>Примечания

Функция-член возвращает значение `!(*this == right)`.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_iterator_operator_ne.cpp
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

## <a name="op_star"></a>  regex_iterator::operator*

Обращается к заданному соответствию.

```cpp
const match_results<BidIt>& operator*();
```

### <a name="remarks"></a>Примечания

Эта функция-член возвращает хранимое значение `match`.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_iterator_operator_star.cpp
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

## <a name="op_add_add"></a>  regex_iterator::operator++

Увеличивает значение итератора.

```cpp
regex_iterator& operator++();
regex_iterator& operator++(int);
```

### <a name="remarks"></a>Примечания

Если текущее совпадение не содержит символы, первый оператор вызывает `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail | regex_constants::match_not_null)`; в противном случае он выполняет переход к сохраненному значению `begin` для указания на первый символ после текущего совпадения, затем вызывает `regex_search(begin, end, match, *pregex, flags | regex_constants::match_prev_avail)`. В любом случае, если поиск заканчивается неудачно, оператор задает для объекта итератор конца последовательности. Оператор возвращает объект.

Второй оператор создает копию объекта, увеличивает объект, а затем возвращает копию.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_iterator_operator_inc.cpp
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

## <a name="op_eq"></a>  regex_iterator::operator=

Сравнивает итераторы на равенство.

```cpp
bool operator==(const regex_iterator& right);
```

### <a name="parameters"></a>Параметры

`right` Итератор для сравнения.

### <a name="remarks"></a>Примечания

Функция-член возвращает значение true, если `*this` и `right` оба являются итераторами конца последовательности, или если ни один из них не является итератором конца последовательности и `begin == right.begin`, `end == right.end`, `pregex == right.pregex`и `flags == right.flags`. В противном случае возвращается значение false.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_iterator_operator_as.cpp
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

## <a name="op_arrow"></a>  regex_iterator::operator-&gt;

Обращается к заданному соответствию.

```cpp
const match_results<BidIt> * operator->();
```

### <a name="remarks"></a>Примечания

Функция-член возвращает адрес сохраненного значения `match`.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_iterator_operator_arrow.cpp
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

## <a name="pointer"></a>  regex_iterator::pointer

Тип указателя на совпадение.

```cpp
typedef match_results<BidIt> *pointer;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для `match_results<BidIt>*`, где `BidIt` — параметр шаблона.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_iterator_pointer.cpp
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

## <a name="reference"></a>  regex_iterator::reference

Тип ссылки на соответствие.

```cpp
typedef match_results<BidIt>& reference;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для `match_results<BidIt>&`, где `BidIt` — параметр шаблона.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_iterator_reference.cpp
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

`first` Начало последовательности для сопоставления.

`last` Конец последовательности для сопоставления.

`re` Регулярное выражение для соответствий.

`f` Флаги для соответствий.

### <a name="remarks"></a>Примечания

Первый конструктор создает итератор конца последовательности. Второй конструктор инициализирует сохраненное значение `begin` значением `first`, сохраненное значение `end` значением `last`, сохраненное значение `pregex` значением `&re`и сохраненное значение `flags` значением `f`. Затем он вызывает `regex_search(begin, end, match, *pregex, flags)`. Если поиск заканчивается неудачно, конструктор задает для объекта итератор конца последовательности.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_iterator_construct.cpp
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

## <a name="regex_type"></a>  regex_iterator::regex_type

Тип регулярного выражения для сопоставления.

```cpp
typedef basic_regex<Elem, RXtraits> regex_type;
```

### <a name="remarks"></a>Примечания

Typedef является синонимом `basic_regex<Elem, RXtraits>`.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_iterator_regex_type.cpp
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

## <a name="value_type"></a>  regex_iterator::value_type

Тип соответствия.

```cpp
typedef match_results<BidIt> value_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для `match_results<BidIt>`, где `BidIt` — параметр шаблона.

### <a name="example"></a>Пример

```cpp
// std__regex__regex_iterator_value_type.cpp
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
