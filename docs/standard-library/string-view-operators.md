---
title: операторы&gt; string_view &lt;
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
ms.openlocfilehash: 699b1f1bddeb71ecbf03297d162a7e45ebd39609
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78890919"
---
# <a name="ltstring_viewgt-operators"></a>операторы&gt; string_view &lt;

Используйте эти операторы для сравнения двух string_viewных объектов, string_view и другого строкового объекта (например, [std:: String](basic-string-class.md)или **char\*** ), для которых предоставляется неявное преобразование. 

||||
|-|-|-|
|[operator!=](#op_neq)|[оператор&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[оператор&lt;](#op_lt)|[operator&lt;&lt;](#op_lt_lt)|[operator&lt;=](#op_lt_eq)|
|[operator==](#op_eq_eq)|[оператор "" ОКП](#op_sv)|

## <a name="op_neq"></a>operator! =

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

*left*\
Любой преобразуемый строковый тип или объект типа `basic_string_view` для сравнения.

*справа*\
Любой преобразуемый строковый тип или объект типа `basic_string_view` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если объект слева от оператора не лексикографически равным объекту с правой стороны; в противном случае — **false**.

### <a name="remarks"></a>Remarks

Неявное преобразование должно существовать из *convertible_string_type* string_view на другой стороне. 

Сравнение основано на парном лексикографическом сравнении последовательностей символов. Если число элементов равно количеству и все элементы равны, то два объекта равны. В противном случае они не равны.

## <a name="op_eq_eq"></a>Оператор = =

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

*left*\
Любой преобразуемый строковый тип или объект типа `basic_string_view` для сравнения.

*справа*\
Любой преобразуемый строковый тип или объект типа `basic_string_view` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если объект в левой части оператора является лексикографически равным объекту с правой стороны; в противном случае — **false**.

### <a name="remarks"></a>Remarks

Неявное преобразование должно существовать из *convertible_string_type* string_view на другой стороне. 

Сравнение основано на парном лексикографическом сравнении последовательностей символов. Если число элементов равно количеству и все элементы равны, то два объекта равны.


## <a name="op_lt">Оператор </a>&lt;

Проверяет, меньше ли объект в левой части оператора, чем объект справа sidestring_view
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

*left*\
Любой преобразуемый строковый тип или объект типа `basic_string_view` для сравнения.

*справа*\
Любой преобразуемый строковый тип или объект типа `basic_string_view` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если объект в левой части оператора лексикографически меньше объекта с правой стороны; в противном случае — **false**.

### <a name="remarks"></a>Remarks

Неявное преобразование должно существовать из *convertible_string_type* string_view на другой стороне. 

Сравнение основано на парном лексикографическом сравнении последовательностей символов. При обнаружении первой неравной пары символов возвращается результат этого сравнения. Если неравные символы не найдены, но одна последовательность короче, более короткая последовательность меньше чем длинная. Иными словами, "Cat" меньше "кошки".

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

## <a name="op_lt_eq"></a>&lt;оператора =

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

*left*\
Любой преобразуемый строковый тип или объект типа `basic_string_view` для сравнения.

*справа*\
Любой преобразуемый строковый тип или объект типа `basic_string_view` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если объект в левой части оператора лексикографически меньше или равен объекту в правой части; в противном случае — **false**.

### <a name="remarks"></a>Remarks

См. [&lt;оператора ](#op_lt).

## <a name="op_lt_lt"></a>&lt;оператора &lt;

Записывает string_view в поток вывода.

```cpp
template <class CharType, class Traits>
inline basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& Ostr, const basic_string_view<CharType, Traits> Str);
```

### <a name="parameters"></a>Параметры

*Ostr*\
поток вывода, в который выполняется запись.

\ *str*
String_view, который необходимо указать в потоке вывода.

### <a name="return-value"></a>Возвращаемое значение

поток вывода, в который выполняется запись.

### <a name="remarks"></a>Remarks

Этот оператор используется для вставки содержимого string_view в поток вывода, например с помощью [std:: cout](iostream.md#cout).

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

*left*\
Любой преобразуемый строковый тип или объект типа `basic_string_view` для сравнения.

*справа*\
Любой преобразуемый строковый тип или объект типа `basic_string_view` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если объект в левой части оператора лексикографически больше объекта string_view с правой стороны; в противном случае — **false**.

### <a name="remarks"></a>Remarks

См. [&lt;оператора ](#op_lt).

## <a name="op_gt_eq"></a>&gt;оператора =

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

*left*\
Любой преобразуемый строковый тип или объект типа `basic_string_view` для сравнения.

*справа*\
Любой преобразуемый строковый тип или объект типа `basic_string_view` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

**true** , если объект слева от оператора лексикографически больше или равен объекту с правой стороны; в противном случае — **false**.

### <a name="remarks"></a>Remarks

См. [&lt;оператора ](#op_lt).

## <a name="op_sv"></a>оператор "ОКП (string_view литерал)

Конструирует string_view из строкового литерала. Требуется `std::literals::string_view_literals`пространства имен. 

### <a name="example"></a>Пример

```cpp

using namespace std;
using namespace literals::string_view_literals;

    string_view sv{ "Hello"sv };
    wstring_view wsv{ L"Hello"sv };
    u16string_view sv16{ u"Hello"sv };
    u32string_view sv32{ U"Hello"sv };
```

## <a name="see-also"></a>См. также раздел

[\<string_view >](../standard-library/string-view.md)
