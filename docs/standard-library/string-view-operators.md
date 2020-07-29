---
title: '&lt;&gt;операторы string_view'
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
ms.openlocfilehash: 39727177ff0fe88e2fcc105a6cee49711b36de6e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222241"
---
# <a name="ltstring_viewgt-operators"></a>&lt;&gt;операторы string_view

Используйте эти операторы для сравнения двух string_view объектов, string_view и другого строкового объекта (например, [std:: String](basic-string-class.md)или **char \* **), для которых предоставляется неявное преобразование.

||||
|-|-|-|
|[operator! =](#op_neq)|[оператор&gt;](#op_gt)|[оператор&gt;=](#op_gt_eq)|
|[оператор&lt;](#op_lt)|[оператор&lt;&lt;](#op_lt_lt)|[оператор&lt;=](#op_lt_eq)|
|[Оператор = =](#op_eq_eq)|[оператор "" ОКП](#op_sv)|

## <a name="operator"></a><a name="op_neq"></a>operator! =

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

*слева*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

*Правильно*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если объект в левой части оператора не лексикографически равным объекту с правой стороны; в противном случае — значение **`false`** .

### <a name="remarks"></a>Remarks

Неявное преобразование должно существовать из *convertible_string_type* string_view на другой стороне.

Сравнение основано на парном лексикографическом сравнении последовательностей символов. Если число элементов равно количеству и все элементы равны, то два объекта равны. В противном случае они не равны.

## <a name="operator"></a><a name="op_eq_eq"></a>Оператор = =

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

*слева*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

*Правильно*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объект слева от оператора лексикографически равен объекту в правой части; в противном случае — значение **`false`** .

### <a name="remarks"></a>Remarks

Неявное преобразование должно существовать из *convertible_string_type* string_view на другой стороне.

Сравнение основано на парном лексикографическом сравнении последовательностей символов. Если число элементов равно количеству и все элементы равны, то два объекта равны.

## <a name="operatorlt"></a><a name="op_lt"></a>станции&lt;

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

*слева*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

*Правильно*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объект слева от оператора лексикографически меньше объекта с правой стороны; в противном случае — значение **`false`** .

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

## <a name="operatorlt"></a><a name="op_lt_eq"></a>станции&lt;=

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

*слева*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

*Правильно*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объект слева от оператора лексикографически меньше или равен объекту в правой части; в противном случае — значение **`false`** .

### <a name="remarks"></a>Remarks

См [. &lt; оператор](#op_lt).

## <a name="operatorltlt"></a><a name="op_lt_lt"></a>станции&lt;&lt;

Записывает string_view в поток вывода.

```cpp
template <class CharType, class Traits>
inline basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& Ostr, const basic_string_view<CharType, Traits> Str);
```

### <a name="parameters"></a>Параметры

*OSTR*\
поток вывода, в который выполняется запись.

*Str*\
String_view, который необходимо указать в потоке вывода.

### <a name="return-value"></a>Возвращаемое значение

поток вывода, в который выполняется запись.

### <a name="remarks"></a>Remarks

Этот оператор используется для вставки содержимого string_view в поток вывода, например с помощью [std:: cout](iostream.md#cout).

## <a name="operatorgt"></a><a name="op_gt"></a>станции&gt;

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

*слева*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

*Правильно*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

### <a name="return-value"></a>Возвращаемое значение

**`true`** Если объект в левой части оператора лексикографически больше, чем объект string_view с правой стороны; в противном случае — значение **`false`** .

### <a name="remarks"></a>Remarks

См [. &lt; оператор](#op_lt).

## <a name="operatorgt"></a><a name="op_gt_eq"></a>станции&gt;=

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

*слева*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

*Правильно*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

### <a name="return-value"></a>Возвращаемое значение

**`true`** значение, если объект слева от оператора лексикографически больше или равен объекту с правой стороны; в противном случае — значение **`false`** .

### <a name="remarks"></a>Remarks

См [. &lt; оператор](#op_lt).

## <a name="operator-sv-string_view-literal"></a><a name="op_sv"></a>оператор "ОКП (string_view литерал)

Конструирует string_view из строкового литерала. Требуется пространство имен `std::literals::string_view_literals` .

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

[\<string_view>](../standard-library/string-view.md)
