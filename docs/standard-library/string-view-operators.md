---
title: '&lt;string_view&gt; операторы'
ms.date: 04/19/2019
f1_keywords:
- xstring/basic_string_view::operator!=
- xstring/basic_string_view::operator&gt;
- xstring/basic_string_view::operator&gt;=
- xstring/basic_string_view::operator&lt;
- xstring/basic_string_view::operator&lt;&lt;
- xstring/basic_string_view::operator&lt;=
- xstring/basic_string_view::operator+
- xstring/basic_string_view::operator==
helpviewer_keywords:
- std::basic_string_view::operator!=
- std::basic_string_view::operator&gt;
- std::basic_string_view::operator&gt;=
- std::basic_string_view::operator&lt;
- std::basic_string_view::operator&lt;&lt;
- std::basic_string_view::operator&lt;=, std::basic_string_view::operator==
ms.openlocfilehash: 1fbb7faf7d6fc92a053c0f4d47575c5c53c7968e
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346922"
---
# <a name="ltstringviewgt-operators"></a>&lt;string_view&gt; операторы

Эти операторы можно использовать для сравнения двух объектов string_view или string_view и либо другого строкового объекта (например [std::string](basic-string-class.md), или **char\***) для предоставляемого неявное преобразование. 

||||
|-|-|-|
|[operator!=](#op_neq)|[оператор&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[оператор&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|
|[operator==](#op_eq_eq)|[оператор» sv «](#op_sv)|

## <a name="op_neq"></a> оператор! =

Проверяет неравенство объекта слева от оператора объекту справа от оператора.

```cpp
template <class CharType, class Traits>
bool operator!=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator!=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator!=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Любой тип можно преобразовать строку или объект типа `basic_string_view` для сравнения.

*right*<br/>
Любой тип можно преобразовать строку или объект типа `basic_string_view` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** не ли объект в левой части оператора лексикографически равен объекту справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Примечания

Должно существовать неявное преобразование из *convertible_string_type* для string_view на другой стороне. 

Сравнение основывается на попарном лексикографическом сравнении последовательностей символов. Если они содержат одинаковое количество элементов, а элементы равны, два объекта равны. В противном случае они не равны.

## <a name="op_eq_eq"></a> оператор ==

Проверяет равенство объекта слева от оператора объекту справа от оператора.

```cpp
template <class CharType, class Traits>
bool operator==(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator==(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator==(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Любой тип можно преобразовать строку или объект типа `basic_string_view` для сравнения.

*right*<br/>
Любой тип можно преобразовать строку или объект типа `basic_string_view` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** значение, если объект в левой части оператора лексикографически равен объекту справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Примечания

Должно существовать неявное преобразование из *convertible_string_type* для string_view на другой стороне. 

Сравнение основывается на попарном лексикографическом сравнении последовательностей символов. Если они содержат одинаковое количество элементов, а элементы равны, два объекта равны.


## <a name="op_lt">Оператор </a>&lt;

Проверяет, что объект слева от оператора меньше, чем объект справа sidestring_view
```cpp
template <class CharType, class Traits>
bool operator<(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator<(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator<(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Любой тип можно преобразовать строку или объект типа `basic_string_view` для сравнения.

*right*<br/>
Любой тип можно преобразовать строку или объект типа `basic_string_view` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если объект в левой части оператора лексикографически меньше, чем объект справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Примечания

Должно существовать неявное преобразование из *convertible_string_type* для string_view на другой стороне. 

Сравнение основывается на попарном лексикографическом сравнении последовательностей символов. При обнаружении первой пары неравных символов, возвращается результат сравнения. Если не найдены никакие символы не равны, но одна последовательность оказывается короче, более короткая последовательность меньше чем более длинная. Другими словами «cat» меньше, чем «коты».

### <a name="example"></a>Пример

```cpp
#include <string>
#include <string_view>

using namespace std;

int main()
{
    string_view sv1 { "ABA" };
    string_view sv2{ "ABAC" };
    string_view sv3{ "ABAD" };
    string_view sv4{ "ABACE" };

    bool result = sv2 > sv1; // true
    result = sv3 > sv2; // true
    result = sv3 != sv1; // true
    result = sv4 < sv3; // true because `C` < `D`
}
```

## <a name="op_lt_eq"></a> Оператор&lt;=

Проверяет, что объект слева от оператора меньше или равен объекту справа от оператора.

```cpp
template <class CharType, class Traits>
bool operator<=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator<=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator<=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Любой тип можно преобразовать строку или объект типа `basic_string_view` для сравнения.

*right*<br/>
Любой тип можно преобразовать строку или объект типа `basic_string_view` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если объект в левой части оператора лексикографически меньше, чем или равен объекту справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Примечания

См. в разделе [оператор&lt;](#op_lt).

## <a name="op_lt_lt"></a> Оператор&lt;&lt;

Записывает string_view в поток вывода.

```cpp
template <class CharType, class Traits>
inline basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& Ostr, const basic_string_view<CharType, Traits> Str);
```

### <a name="parameters"></a>Параметры

*Ostr*<br/>
выполняется запись в поток вывода.

*STR*<br/>
String_view, которое необходимо ввести в поток вывода.

### <a name="return-value"></a>Возвращаемое значение

выполняется запись в поток вывода.

### <a name="remarks"></a>Примечания

Этот оператор используется для вставки содержимого string_view в поток вывода, например с помощью [std::cout](iostream.md#cout).

## <a name="op_gt">Оператор </a>&gt;

Проверяет, что объект слева от оператора больше, чем объект справа от оператора.

```cpp
template <class CharType, class Traits>
bool operator>(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator>(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator>(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Любой тип можно преобразовать строку или объект типа `basic_string_view` для сравнения.

*right*<br/>
Любой тип можно преобразовать строку или объект типа `basic_string_view` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** значение, если объект в левой части оператора лексикографически больше, чем объект string_view справа от оператора; в противном случае **false**.

### <a name="remarks"></a>Примечания

См. в разделе [оператор&lt;](#op_lt).

## <a name="op_gt_eq"></a> Оператор&gt;=

Проверяет, что объект слева от оператора больше или равен объекту справа от оператора.

```cpp
template <class CharType, class Traits>
bool operator>=(
    const basic_string_view<CharType, Traits>& left,
    const basic_string_view<CharType, Traits>& right);

template <class CharType, class Traits>
bool operator>=(
    const basic_string_view<CharType, Traits>& left,
    convertible_string_type right);

template <class CharType, class Traits>
bool operator>=(
    convertible_string_type left,
    const basic_string_view<CharType, Traits>& right);
```

### <a name="parameters"></a>Параметры

*left*<br/>
Любой тип можно преобразовать строку или объект типа `basic_string_view` для сравнения.

*right*<br/>
Любой тип можно преобразовать строку или объект типа `basic_string_view` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** значение, если объект в левой части оператора лексикографически больше или равен объекту справа от оператора; в противном случае — значение **false**.

### <a name="remarks"></a>Примечания

См. в разделе [оператор&lt;](#op_lt).

## <a name="op_sv"></a> оператор»» sv (string_view литерала)

Создает string_view из строкового литерала. Требует объявления пространства имен `std::literals::string_view_literals`. 

### <a name="example"></a>Пример

```cpp

using namespace std;
using namespace literals::string_view_literals;

    string_view sv{ "Hello"sv };
    wstring_view wsv{ L"Hello"sv };
    u16string_view sv16{ u"Hello"sv };
    u32string_view sv32{ U"Hello"sv };
```

## <a name="see-also"></a>См. также

[\<string_view >](../standard-library/string-view.md)<br/>
