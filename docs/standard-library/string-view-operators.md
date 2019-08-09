---
title: '&lt;операторы&gt; string_view'
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
ms.openlocfilehash: caa6e515428cc0ea767eef20e819753c8f7ff8f9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459220"
---
# <a name="ltstringviewgt-operators"></a>&lt;операторы&gt; string_view

Используйте эти операторы для сравнения двух объектов string_view, string_view и другого строкового объекта (например, [std:: String](basic-string-class.md)или **char\*** ), для которых предоставляется неявное преобразование. 

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

*слева*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

*Правильно*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если объект слева от оператора не лексикографически равным объекту с правой стороны; в противном случае — **false**.

### <a name="remarks"></a>Примечания

Неявное преобразование должно существовать из *convertible_string_type* в string_view с другой стороны. 

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

*слева*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

*Правильно*\
Любой преобразуемый строковый тип или объект `basic_string_view` сравниваемого типа.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если объект в левой части оператора является лексикографически равным объекту с правой стороны; в противном случае — **false**.

### <a name="remarks"></a>Примечания

Неявное преобразование должно существовать из *convertible_string_type* в string_view с другой стороны. 

Сравнение основано на парном лексикографическом сравнении последовательностей символов. Если число элементов равно количеству и все элементы равны, то два объекта равны.


## <a name="op_lt"></a> Оператор&lt;

Проверяет, меньше ли объект в левой части оператора, чем объект в правой части sidestring_view
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

**значение true** , если объект в левой части оператора лексикографически меньше объекта с правой стороны; в противном случае — **false**.

### <a name="remarks"></a>Примечания

Неявное преобразование должно существовать из *convertible_string_type* в string_view с другой стороны. 

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

## <a name="op_lt_eq"></a>станции&lt;=

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

**значение true** , если объект в левой части оператора лексикографически меньше или равен объекту в правой части; в противном случае — **false**.

### <a name="remarks"></a>Примечания

См [.&lt;оператор](#op_lt).

## <a name="op_lt_lt"></a>станции&lt;&lt;

Записывает string_view в выходной поток.

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

### <a name="remarks"></a>Примечания

Этот оператор используется для вставки содержимого string_view в выходной поток, например с помощью [std:: cout](iostream.md#cout).

## <a name="op_gt"></a> Оператор&gt;

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

**значение true** , если объект в левой части оператора лексикографически больше, чем объект string_view в правой части; в противном случае — **false**.

### <a name="remarks"></a>Примечания

См [.&lt;оператор](#op_lt).

## <a name="op_gt_eq"></a>станции&gt;=

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

**true** , если объект слева от оператора лексикографически больше или равен объекту с правой стороны; в противном случае — **false**.

### <a name="remarks"></a>Примечания

См [.&lt;оператор](#op_lt).

## <a name="op_sv"></a>оператор "ОКП (литерал string_view)

Конструирует string_view из строкового литерала. Требуется пространство `std::literals::string_view_literals`имен. 

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

[\<string_view >](../standard-library/string-view.md)
