---
title: Класс basic_string_view
ms.date: 04/20/2019
f1_keywords:
- xstring/std::basic_string_view
- xstring/std::basic_string_view::allocator_type
- xstring/std::basic_string_view::const_iterator
- xstring/std::basic_string_view::const_pointer
- xstring/std::basic_string_view::const_reference
- xstring/std::basic_string_view::const_reverse_iterator
- xstring/std::basic_string_view::difference_type
- xstring/std::basic_string_view::iterator
- xstring/std::basic_string_view::npos
- xstring/std::basic_string_view::pointer
- xstring/std::basic_string_view::reference
- xstring/std::basic_string_view::reverse_iterator
- xstring/std::basic_string_view::size_type
- xstring/std::basic_string_view::traits_type
- xstring/std::basic_string_view::value_type
- xstring/std::basic_string_view::append
- xstring/std::basic_string_view::assign
- xstring/std::basic_string_view::at
- xstring/std::basic_string_view::back
- xstring/std::basic_string_view::begin
- xstring/std::basic_string_view::c_str
- xstring/std::basic_string_view::capacity
- xstring/std::basic_string_view::cbegin
- xstring/std::basic_string_view::cend
- xstring/std::basic_string_view::clear
- xstring/std::basic_string_view::compare
- xstring/std::basic_string_view::copy
- xstring/std::basic_string_view::_Copy_s
- xstring/std::basic_string_view::crbegin
- xstring/std::basic_string_view::crend
- xstring/std::basic_string_view::data
- xstring/std::basic_string_view::empty
- xstring/std::basic_string_view::end
- xstring/std::basic_string_view::erase
- xstring/std::basic_string_view::find
- xstring/std::basic_string_view::find_first_not_of
- xstring/std::basic_string_view::find_first_of
- xstring/std::basic_string_view::find_last_not_of
- xstring/std::basic_string_view::find_last_of
- xstring/std::basic_string_view::front
- xstring/std::basic_string_view::get_allocator
- xstring/std::basic_string_view::insert
- xstring/std::basic_string_view::length
- xstring/std::basic_string_view::max_size
- xstring/std::basic_string_view::pop_back
- xstring/std::basic_string_view::push_back
- xstring/std::basic_string_view::rbegin
- xstring/std::basic_string_view::rend
- xstring/std::basic_string_view::remove_prefix
- xstring/std::basic_string_view::remove_suffix
- xstring/std::basic_string_view::replace
- xstring/std::basic_string_view::reserve
- xstring/std::basic_string_view::resize
- xstring/std::basic_string_view::rfind
- xstring/std::basic_string_view::shrink_to_fit
- xstring/std::basic_string_view::size
- xstring/std::basic_string_view::substr
- xstring/std::basic_string_view::swap
helpviewer_keywords:
- std::basic_string_view
- std::basic_string_view, allocator_type
- std::basic_string_view, const_iterator
- std::basic_string_view, const_pointer
- std::basic_string_view, const_reference
- std::basic_string_view, const_reverse_iterator
- std::basic_string_view, difference_type
- std::basic_string_view, iterator
- std::basic_string_view, npos
- std::basic_string_view, pointer
- std::basic_string_view, reference
- std::basic_string_view, reverse_iterator
- std::basic_string_view, size_type
- std::basic_string_view, traits_type
- std::basic_string_view, value_type
- std::basic_string_view, append
- std::basic_string_view, assign
- std::basic_string_view, at
- std::basic_string_view, back
- std::basic_string_view, begin
- std::basic_string_view, c_str
- std::basic_string_view, capacity
- std::basic_string_view, cbegin
- std::basic_string_view, cend
- std::basic_string_view, clear
- std::basic_string_view, compare
- std::basic_string_view, copy
- std::basic_string_view, crbegin
- std::basic_string_view, crend
- std::basic_string_view, data
- std::basic_string_view, empty
- std::basic_string_view, end
- std::basic_string_view, erase
- std::basic_string_view, find
- std::basic_string_view, find_first_not_of
- std::basic_string_view, find_first_of
- std::basic_string_view, find_last_not_of
- std::basic_string_view, find_last_of
- std::basic_string_view, front
- std::basic_string_view, get_allocator
- std::basic_string_view, insert
- std::basic_string_view, length
- std::basic_string_view, max_size
- std::basic_string_view, pop_back
- std::basic_string_view, push_back
- std::basic_string_view, rbegin
- std::basic_string_view, rend
- std::basic_string_view, remove_prefix
- std::basic_string_view, remove_suffix
- std::basic_string_view, replace
- std::basic_string_view, reserve
- std::basic_string_view, resize
- std::basic_string_view, rfind
- std::basic_string_view, shrink_to_fit
- std::basic_string_view, size
- std::basic_string_view, substr
- std::basic_string_view, swap
ms.assetid: a9c3e0a2-39bf-4c8a-b093-9abe30839591
ms.openlocfilehash: ac65dca931f821c717e9c081c8d3479fd0b3bb0e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364893"
---
# <a name="basic_string_view-class"></a>Класс basic_string_view

Шаблон `basic_string_view<charT>` класса был добавлен в C-17, чтобы служить безопасным и эффективным способом для функции принимать различные несвязанные типы строк без необходимости быть освоены на этих типах. Класс содержит невладеющий указателем на смежную последовательность данных символов и длину, которая определяет количество символов в последовательности. Не делается никаких предположений относительно того, является ли последовательность нулевым.

Стандартная библиотека определяет несколько специализаций в зависимости от типа элементов:

- `string_view`
- `wstring_view`
- `u16string_view`
- `u32string_view`

В этом документе термин "string_view" обычно относится к любому из этих типов.

В string_view описывается минимальный общий интерфейс, необходимый для чтения строковых данных. Он обеспечивает констадный доступ к базовым данным; он не делает никаких `copy` копий (за исключением функции). Данные могут содержать или не содержать нулевых значений ('0') в любой позиции. String_view не имеет контроля над сроком службы объекта. Абонент несет ответственность за достоверность данных строки, лежащих в основе строки.

Функция, которая принимает параметр типа string_view может быть сделана для работы с любым типом строки, не превращая функцию в шаблон или ограничивая функцию определенным подмножеством типов строк. Единственным требованием является то, что неявное преобразование существует от типа строки к string_view. Все стандартные типы строк неявно конвертируемы для string_view, содержащей один и тот же тип элемента. Другими словами, является `std::string` кабриолет, `string_view` но не `wstring_view`в .

В следующем примере показана `f` функция нешаблона, которая выполняет параметр типа. `wstring_view` Его можно назвать с аргументами `wchar_t*`типа `winrt::hstring` `std::wstring`, и .

```cpp
// compile with: /std:c++17
// string_view that uses elements of wchar_t
void f(wstring_view);

// pass a std::wstring:
const std::wstring& s { L"Hello" };
f(s);

// pass a C-style null-terminated string (string_view is not null-terminated):
const wchar_t* ns = L"Hello";
f(ns);

// pass a C-style character array of len characters (excluding null terminator):
const wchar_t* cs { L"Hello" };
size_t len { 5 };
f({cs,len});

// pass a WinRT string
winrt::hstring hs { L"Hello" };
f(hs);
```

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType, class Traits = char_traits<CharType>>
class basic_string_view;
```

### <a name="parameters"></a>Параметры

*Chartype*\
Тип символов, которые хранятся в string_view. Стандартная библиотека СЗ предоставляет следующие типы для специализаций этого шаблона.

- [string_view](../standard-library/string-view-typedefs.md#string_view) для элементов типа **char**
- [wstring_view](../standard-library/string-view-typedefs.md#wstring_view), для **wchar_t**
- [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) для **char16_t**
- [u32string_view](../standard-library/string-view-typedefs.md#u32string_view) для **char32_t**.

*Черты*\
По умолчанию [char_traits](char-traits-struct.md)<*> CharType.*

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_string_view](#basic_string_view)|Строит string_view, которая пуста, или же указывает на все или часть данных какого-либо другого объекта строки, или на массив символов C-стиля.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|**const_iterator**|Случайный доступ итератор, который может читать **конст** элементы.|
|**const_pointer**|`using const_pointer = const value_type*;`|
|**const_reference**|`using const_reference = const value_type&;`|
|**const_reverse_iterator**|`using const_reverse_iterator = std::reverse_iterator<const_iterator>;`|
|**difference_type**|`using difference_type = ptrdiff_t;`|
|**Итератор**|`using iterator = const_iterator;`|
|**npos**|`static constexpr size_type npos = size_type(-1);`|
|**указатель**|`using pointer = value_type*;`|
|**Ссылки**|`using reference = value_type&;`|
|**reverse_iterator**|`using reverse_iterator = const_reverse_iterator;`|
|**size_type**|`using size_type = size_t;`|
|**traits_type**|`using traits_type = Traits;`|
|**Value_type**|`using value_type = CharType;`|

### <a name="member-operators"></a>Операторы-члены

|Оператор|Описание|
|-|-|
|[оператора](#op_eq)|Присваивая объект струны string_view или кабриолету другому string_view.|
|[Оператор\[\]](#op_at)|Возвращает элемент по указанному индексу.|

### <a name="member-functions"></a>Функции элементов

|Функция-член|Описание|
|-|-|
|[В](#at)|Возвращает const_reference элементу в указанном месте.|
|[Назад](#back)|Возвращает const_reference к последнему элементу.|
|[Начать](#begin)|Возвращает конст-итератор, обративщееся к первому элементу. (string_views непреложны.)|
|[cbegin](#cbegin)|То же самое, что [начать](#begin).|
|[cend](#cend)|Возвращает конст-итератор, который указывает на один мимо последнего элемента.|
|[Копировать](#copy)|Копирует не более определенного количества символов из индексированного положения в исходном string_view к целевому массиву символов. (Не рекомендуется. Вместо этого используйте _Copy_s.)|
|[_Copy_s](#_copy_s)|Безопасная функция копирования CRT.|
|[Сравнить](#compare)|Сравнивает string_view с указанным string_view определить, равны ли они или он лексикографически меньше другого.|
|[crbegin](#crbegin)|То же, что [и rbegin](#rbegin).|
|[crend](#crend)|То же самое, что [и ренд](#rend).|
|[данные](#data)|Возвращает необработанный невладеющий указателем в последовательность символов.|
|[Пустой](#empty)|Тестирует, содержит ли string_view символы.|
|[end](#end)|То же самое, что [и cend](#cend).|
|[Найти](#find)|Поиск в переднем направлении для первого появления подстроки, которая соответствует заданной последовательности символов.|
|[find_first_not_of](#find_first_not_of)|Поиск первого символа, который не является элементом указанного string_view или кабриолетовый объект строки.|
|[find_first_of](#find_first_of)|Поиск первого символа, который соответствует любому элементу указанного string_view или кабриолету объекта строки.|
|[find_last_not_of](#find_last_not_of)|Поиск последнего символа, который не является элементом указанного string_view или кабриолетом объекта строки.|
|[find_last_of](#find_last_of)|Поиск последнего символа, который является элементом указанного string_view или кабриолетовый объект строки.|
|[Перед](#front)|Возвращает const_reference к первому элементу.|
|[длина](#length)|Возвращает текущее количество элементов.|
|[max_size](#max_size)|Возвращает максимальное количество символов, которые может содержать string_view.|
|[rbegin](#rbegin)|Возвращает конст-итератор, который обращается к первому элементу в обратном string_view.|
|[remove_prefix](#remove_prefix)|Перемещает указатель вперед по указанному числу элементов.|
|[remove_suffix](#remove_suffix)|Уменьшает размер представления на указанное количество элементов, начиная со спины.|
|[rend](#rend)|Возвращает конст-итератор, который указывает на один последний элемент в обратном string_view.|
|[rfind](#rfind)|Поиск string_view в обратном направлении для первого появления подстроки, которая соответствует заданной последовательности символов.|
|[Размер](#size)|Возвращает текущее количество элементов.|
|[substr](#substr)|Возвращает подстроку заданной длины, начиная с заданного индекса.|
|[Своп](#swap)|Обменяйся содержимым двух string_views.|

## <a name="remarks"></a>Remarks

Если функция должна создать последовательность, длина которой превышает [max_size](#max_size) элементов, функция выдает сообщение об ошибке длины, создавая объект типа [length_error](../standard-library/length-error-class.md).

## <a name="requirements"></a>Требования

[std:c'17](../build/reference/std-specify-language-standard-version.md) или позже

**Заголовок:** \<string_view>

**Пространство имен:** std

## <a name="basic_string_viewat"></a><a name="at"></a>basic_string_view::at

Возвращает const_reference символу в указанном 0-уровне индекса.

```cpp
constexpr const_reference at(size_type offset) const;
```

### <a name="parameters"></a>Параметры

*Смещение*\
Индекс элемента, на который следует ссылаться.

### <a name="return-value"></a>Возвращаемое значение

На const_reference символу в позиции, указанной индексом параметров.

### <a name="remarks"></a>Remarks

Первый элемент имеет индекс нуля, а следующие элементы индексируются последовательно положительными целыми рядами, так что string_view длины *n* имеет *n-й*элемент, индексированный числом *n -* 1. **при** бросках исключение для недействительных индексов, в отличие от [оператора.\[](#op_at)

В общем, мы **рекомендуем,** чтобы `std::vector` для последовательностей, таких как и string_view никогда не должны использоваться. Недействительный индекс, передаваемый в последовательность, является ошибкой логики, которая должна быть обнаружена и исправлена во время разработки. Если программа не совсем уверена в том, что ее индексы действительны, она должна проверить их, а не вызывать () и полагаться на исключения для защиты от неосторожного программирования.

Смотрите [basic_string_view::оператор\[ ](#op_at) для получения дополнительной информации.

### <a name="example"></a>Пример

```cpp
// basic_string_view_at.cpp
// compile with: /EHsc
#include <string_view>
#include <iostream>

int main()
{
    using namespace std;

    const string_view  str1("Hello world");
    string_view::const_reference refStr2 = str1.at(8); // 'r'
}
```

## <a name="basic_string_viewback"></a><a name="back"></a>basic_string_view::back

Возвращает const_reference к последнему элементу.

```cpp
constexpr const_reference back() const;
```

### <a name="return-value"></a>Возвращаемое значение

В string_view const_reference до последнего элемента.

### <a name="remarks"></a>Remarks

Бросает исключение, если string_view пусто.

Имейте в виду, что после изменения string_view, например, при вызове, `remove_suffix`тогда элемент, возвращенный этой функцией, больше не является последним элементом в базовых данных.

### <a name="example"></a>Пример

string_view, которая построена с строкой C буквальноней не включает в себя `back` прекращение null и, следовательно, в следующем примере возвращает 'p', а не 'No0'.

```cpp
char c[] = "Help"; // char[5]
string_view sv{ c };
cout << sv.size(); // size() == 4
cout << sv.back() << endl; // p
```

Встроенные нули рассматриваются как любой другой символ:

```cpp
string_view e = "embedded\0nulls"sv;
cout << boolalpha << (e.back() == 's'); // true
```

## <a name="basic_string_viewbasic_string_view"></a><a name="basic_string_view"></a>basic_string_view::basic_string_view

Строит string_view.

```cpp
constexpr basic_string_view() noexcept;
constexpr basic_string_view(const basic_string_view&) noexcept = default;
constexpr basic_string_view(const charT* str);
constexpr basic_string_view(const charT* str, size_type len);
```

### <a name="parameters"></a>Параметры

*Ул*\
Указатель на значения символов.

*Лен*\
Количество символов, которые можно включить в представление.

## <a name="remarks"></a>Remarks

Конструкторы с параметром charT, предполагают, что вход ный минимум завершен, но терминnulling null не входит в string_view.

Вы также можете построить string_view с буквальным. Смотрите [оператора""sv](string-view-operators.md#op_sv).

## <a name="basic_string_viewbegin"></a><a name="begin"></a>basic_string_view::начало

То же, [что и cbegin](#cbegin).

```cpp
constexpr const_iterator begin() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает const_iterator, обращаясь к первому элементу.

## <a name="basic_string_viewcbegin"></a><a name="cbegin"></a>basic_string_view:cbegin

Возвращает const_iterator, которая обращается к первому элементу в диапазоне.

```cpp
constexpr const_iterator cbegin() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**Конст** случайный доступ итератор, который указывает на первый элемент диапазона, или расположение только за пределами конца пустого диапазона (для пустого диапазона, `cbegin() == cend()`).

## <a name="basic_string_viewcend"></a><a name="cend"></a>basic_string_view::cend

Возвращает const_iterator, которая обращается к местоположению только за пределами последнего элемента в диапазоне.

```cpp
constexpr const_iterator cend() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**Конст** случайный доступ итератор, который указывает только за пределами конца диапазона.

### <a name="remarks"></a>Remarks

Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.

## <a name="basic_string_viewcompare"></a><a name="compare"></a>basic_string_view::compare

Выполняет сравнение чувствительного к делу с указанным string_view (или кабриолет типа строки), чтобы определить, являются ли эти два объекта равными или один из них лексикографически меньше, чем другой. Операторы string_view [ \<>](string-view-operators.md) используют эту функцию участника для выполнения сравнений.

```cpp
constexpr int compare(basic_string_view strv) const noexcept;
constexpr int compare(size_type pos, size_type num, basic_string_view strv) const;
constexpr int compare(size_type pos, size_type num, basic_string_view strv, size_type offset, size_type num2) const;
constexpr int compare(const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr, size_type num2) const;
```

### <a name="parameters"></a>Параметры

*strv*\
String_view, которую следует сравнить с этой string_view.

*Pos*\
Индекс этого string_view с которого начинается сравнение.

*Num*\
Максимальное количество символов из этого string_view для сопоставления.

*num2*\
Максимальное количество символов из *strv,* которые необходимо сравнить.

*Смещение*\
Индекс *стрва,* с которого начинается сравнение.

*Ptr*\
Строка C, сравнимые с этой string_view.

### <a name="return-value"></a>Возвращаемое значение

Отрицательное значение, если это string_view меньше, чем *strv* или *ptr;* нулевой, если две последовательности символов равны; или положительное значение, если это string_view больше, чем *strv* или *ptr*.

### <a name="remarks"></a>Remarks

Функции `compare` участника выполняют конкретное сравнение всех или части каждой последовательности символов.

### <a name="example"></a>Пример

```cpp
// basic_string_view_compare.cpp
// compile with: /EHsc
#include <string_view>
#include <iostream>
#include <string>

using namespace std;

string to_alpha(int result)
{
   if (result < 0) return " less than ";
   else if (result == 0) return " equal to ";
   else return " greater than ";
}

int main()
{
   // The first member function compares
   // two string_views
   string_view sv_A("CAB");
   string_view sv_B("CAB");
   cout << "sv_A is " << sv_A << endl;
   cout << "sv_B is " << sv_B << endl;
   int comp1 = sv_A.compare(sv_B);
   cout << "sv_A is" << to_alpha(comp1) << "sv_B.\n";

   // The second member function compares part of
   // an operand string_view to another string_view
   string_view sv_C("AACAB");
   string_view sv_D("CAB");
   cout << "sv_C is: " << sv_C << endl;
   cout << "sv_D is: " << sv_D << endl;
   int comp2a = sv_C.compare(2, 3, sv_D);
   cout << "The last three characters of sv_C are"
       << to_alpha(comp2a) << "sv_D.\n";

   int comp2b = sv_C.compare(0, 3, sv_D);
   cout << "The first three characters of sv_C are"
       << to_alpha(comp2b) << "sv_D.\n";

   // The third member function compares part of
   // an operand string_view to part of another string_view
   string_view sv_E("AACAB");
   string_view sv_F("DCABD");
   cout << "sv_E: " << sv_E << endl;
   cout << "sv_F is: " << sv_F << endl;
   int comp3a = sv_E.compare(2, 3, sv_F, 1, 3);
   cout << "The three characters from position 2 of sv_E are"
       << to_alpha(comp3a)
       << "the 3 characters of sv_F from position 1.\n";

   // The fourth member function compares
   // an operand string_view to a C string
   string_view sv_G("ABC");
   const char* cs_A = "DEF";
   cout << "sv_G is: " << sv_G << endl;
   cout << "cs_A is: " << cs_A << endl;
   int comp4a = sv_G.compare(cs_A);
   cout << "sv_G is" << to_alpha(comp4a) << "cs_A.\n";

   // The fifth member function compares part of
   // an operand string_view to a C string
   string_view sv_H("AACAB");
   const char* cs_B = "CAB";
   cout << "sv_H is: " << sv_H << endl;
   cout << "cs_B is: " << cs_B << endl;
   int comp5a = sv_H.compare(2, 3, cs_B);
   cout << "The last three characters of sv_H are"
      << to_alpha(comp5a) << "cs_B.\n";

   // The sixth member function compares part of
   // an operand string_view to part of an equal length of
   // a C string
   string_view sv_I("AACAB");
   const char* cs_C = "ACAB";
   cout << "sv_I is: " << sv_I << endl;
   cout << "cs_C: " << cs_C << endl;
   int comp6a = sv_I.compare(1, 3, cs_C, 3);
   cout << "The 3 characters from position 1 of sv_I are"
      << to_alpha(comp6a) << "the first 3 characters of cs_C.\n";
}
```

```Output
sv_A is CAB
sv_B is CAB
sv_A is equal to sv_B.
sv_C is: AACAB
sv_D is: CAB
The last three characters of sv_C are equal to sv_D.
The first three characters of sv_C are less than sv_D.
sv_E: AACAB
sv_F is: DCABD
The three characters from position 2 of sv_E are equal to the 3 characters of sv_F from position 1.
sv_G is: ABC
cs_A is: DEF
sv_G is less than cs_A.
sv_H is: AACAB
cs_B is: CAB
The last three characters of sv_H are equal to cs_B.
sv_I is: AACAB
cs_C: ACAB
The 3 characters from position 1 of sv_I are equal to the first 3 characters of cs_C.
```

## <a name="basic_string_viewcopy"></a><a name="copy"></a>basic_string_view::копия

Копирует не более определенного количества символов из индексированного положения в исходном string_view к целевому массиву символов. Мы рекомендуем использовать безопасную функцию [basic_string_view::_Copy_s](#_copy_s) вместо этого.

```cpp
size_type copy(charT* ptr, size_type count, size_type offset = 0) const;
```

### <a name="parameters"></a>Параметры

*Ptr*\
Целевой массив символов, в который должны быть скопированы элементы.

*Рассчитывать*\
Количество символов, которые будут скопированы, в лучшем случае, из источника string_view.

*Смещение*\
Исходное положение в исходном string_view из которого должны быть сделаны копии.

### <a name="return-value"></a>Возвращаемое значение

Число фактически скопированных символов.

### <a name="remarks"></a>Remarks

Символ NULL не добавляется в конец копии.

## <a name="basic_string_view_copy_s"></a><a name="_copy_s"></a>basic_string_view::_Copy_s

Безопасная функция копирования CRT, которая будет использоваться вместо [копии.](#copy)

```cpp
size_type _Copy_s(
    value_type* dest,
    size_type dest_size,
    size_type count,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>Параметры

*Dest*\
Целевой массив символов, в который должны быть скопированы элементы.

*dest_size*\
Размер *dest*.

*Подсчитайте* количество символов, которые будут скопированы, в лучшем случае, из строки исходного кода.

*_off*\
Начальная позиция в исходной строке, из которой должны быть сделаны копии.

### <a name="return-value"></a>Возвращаемое значение

Число фактически скопированных символов.

### <a name="remarks"></a>Remarks

Символ NULL не добавляется в конец копии.

Для получения дополнительной информации [см.](../c-runtime-library/security-features-in-the-crt.md)

## <a name="basic_string_viewcrbegin"></a><a name="crbegin"></a>basic_string_view::crbegin

Возвращает const_reverse_iterator, которая обращается к первому элементу в обратном string_view.

```cpp
constexpr const_reverse_iterator crbegin() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Const_reverse_iterator, которая рассматривает первый элемент в обратном string_view.

## <a name="basic_string_viewcrend"></a><a name="crend"></a>basic_string_view::crend

То же самое, что [и ренд](#rend).

```cpp
constexpr const_reverse_iterator crend() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает const_reverse_iterator, который обращается к одному за окончанием обратного string_view.

## <a name="basic_string_viewdata"></a><a name="data"></a>basic_string_view::dата

Возвращает необработанный невладеющий указателем в последовательность символов объекта, который использовался для построения string_view.

```cpp
constexpr value_type *data() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель к началу первого элемента последовательности символов.

### <a name="remarks"></a>Remarks

Указатель не может изменять символы.

Последовательность string_view символов не обязательно сводится на нет. Тип возврата `data` не является допустимой строкой C, потому что ни один нулевой символ не придатим. Нулевой символ 'No0' не имеет особого значения в объекте типа string_view и может быть частью string_view объекта, как и любой другой символ.

## <a name="basic_string_viewempty"></a><a name="empty"></a>basic_string_view::пустой

Тестирует, содержит ли string_view символы или нет.

```cpp
constexpr bool empty() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если объект string_view не содержит символов; **ложно,** если он имеет по крайней мере один символ.

### <a name="remarks"></a>Remarks

Функция члена эквивалентна [размеру](#size)() q 0.

## <a name="basic_string_viewend"></a><a name="end"></a>basic_string_view::end

Возвращает случайный доступ const_iterator, который указывает на один последний элемент.

```cpp
constexpr const_iterator end() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает случайный доступ const_iterator, который указывает на один последний элемент.

### <a name="remarks"></a>Remarks

`end`используется для проверки того, достиг ли const_iterator конец своего string_view. Значение, возвращаемое `end`, не должно быть подвергнуто удалению ссылки.

## <a name="basic_string_viewfind"></a><a name="find"></a>basic_string_view::найти

Поиск string_view в переднем направлении для первого появления символа или подстроки, которая соответствует заданной последовательности символов (ы).

```cpp
constexpr size_type find(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>Параметры

*Ул*\
В string_view, для которой функция члена является поиск.

*chVal*\
Значение символа, для которого следует искать функцию-член.

*Смещение*\
Индекс, с которого должен начаться поиск.

*Ptr*\
Строка C, для которой функция члена предназначена для поиска.

*Рассчитывать*\
Количество символов в *ptr,* отсчитывая вперед от первого персонажа.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого символа искомой подстроки, если она успешно найдена; в противном случае — `npos`.

## <a name="basic_string_viewfind_first_not_of"></a><a name="find_first_not_of"></a>basic_string_view::find_first_not_of

Поиск первого символа, который не является элементом указанного объекта string_view или кабриолетстроки.

```cpp
constexpr size_type find_first_not_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>Параметры

*Ул*\
В string_view, для которой функция члена является поиск.

*chVal*\
Значение символа, для которого следует искать функцию-член.

*Смещение*\
Индекс, с которого должен начаться поиск.

*Ptr*\
Строка C, для которой функция члена предназначена для поиска.

*Рассчитывать*\
Количество символов, отсчитывающих вперед от первого символа, в строке C, для которой функция участника предназначена для поиска.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого символа искомой подстроки, если она успешно найдена; в противном случае — `npos`.

## <a name="basic_string_viewfind_first_of"></a><a name="find_first_of"></a>basic_string_view::find_first_of

Поиск первого символа, который соответствует любому элементу указанного string_view.

```cpp
constexpr size_type find_first_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(const charT* str, size_type offset, size_type count) const;
constexpr size_type find_first_of(const charT* str, size_type offset = 0) const;
```

### <a name="parameters"></a>Параметры

*chVal*\
Значение символа, для которого следует искать функцию-член.

*Смещение*\
Индекс, с которого должен начаться поиск.

*Ptr*\
Строка C, для которой функция члена предназначена для поиска.

*Рассчитывать*\
Количество символов, отсчитывающих вперед от первого символа, в строке C, для которой функция участника предназначена для поиска.

*Ул*\
В string_view, для которой функция члена является поиск.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого символа искомой подстроки, если она успешно найдена; в противном случае — `npos`.

## <a name="basic_string_viewfind_last_not_of"></a><a name="find_last_not_of"></a>basic_string_view::find_last_not_of

Поиск последнего символа, который не является элементом указанного string_view.

```cpp
constexpr size_type find_last_not_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Параметры

*Ул*\
В string_view, для которой функция члена является поиск.

*chVal*\
Значение символа, для которого следует искать функцию-член.

*Смещение*\
Индекс, по которому должен завершиться поиск.

*Ptr*\
Строка C, для которой функция члена предназначена для поиска.

*Рассчитывать*\
Количество символов, отсчитывающих вперед от первого персонажа, в *ptr*.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого символа искомой подстроки, если она успешно найдена; в противном случае — `string_view::npos`.

## <a name="basic_string_viewfind_last_of"></a><a name="find_last_of"></a>basic_string_view::find_last_of

Поиск последнего символа, который соответствует любому элементу указанного string_view.

```cpp
constexpr size_type find_last_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Параметры

*Ул*\
В string_view, для которой функция члена является поиск.

*chVal*\
Значение символа, для которого следует искать функцию-член.

*Смещение*\
Индекс, по которому должен завершиться поиск.

*Ptr*\
Строка C, для которой функция члена предназначена для поиска.

*Рассчитывать*\
Количество символов, отсчитывающих вперед от первого символа, в строке C, для которой функция участника предназначена для поиска.

### <a name="return-value"></a>Возвращаемое значение

Индекс последнего символа искомой подстроки, если он был успешно найден; в противном случае — `npos`.

## <a name="basic_string_viewfront"></a><a name="front"></a>basic_string_view::фронт

Возвращает const_reference к первому элементу.

```cpp
constexpr const_reference front() const;
```

### <a name="return-value"></a>Возвращаемое значение

В const_reference к первому элементу.

### <a name="remarks"></a>Remarks

Бросает исключение, если string_view пусто.

## <a name="basic_string_viewlength"></a><a name="length"></a>basic_string_view::длина

Возвращает текущее количество элементов.

```cpp
constexpr size_type length() const noexcept;
```

### <a name="remarks"></a>Remarks

Функция-член такая же, как [size](#size).

## <a name="basic_string_viewmax_size"></a><a name="max_size"></a>basic_string_view::max_size

Возвращает максимальное количество символов, которые может содержать string_view.

```cpp
constexpr size_type max_size() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное количество символов, которые может содержать string_view.

### <a name="remarks"></a>Remarks

Исключение типа [length_error](../standard-library/length-error-class.md) выбрасывается, когда операция производит string_view `max_size()`длиной больше, чем .

## <a name="basic_string_viewoperator"></a><a name="op_eq"></a>basic_string_view:оператор

Присваивая объект струны string_view или кабриолету другому string_view.

```cpp
constexpr basic_string_view& operator=(const basic_string_view&) noexcept = default;
```

### <a name="example"></a>Пример

```cpp
   string_view s = "Hello";
   string_view s2 = s;
```

## <a name="basic_string_viewoperator"></a><a name="op_at"></a>basic_string_view:оператор

Обеспечивает const_reference символу с указанным индексом.

```cpp
constexpr const_reference operator[](size_type offset) const;
```

### <a name="parameters"></a>Параметры

*Смещение*\
Индекс элемента, на который следует ссылаться.

### <a name="return-value"></a>Возвращаемое значение

На const_reference символу в позиции, указанной индексом параметров.

### <a name="remarks"></a>Remarks

Первый элемент имеет индекс нуля, а следующие элементы индексируются последовательно положительными целыми рядами, так что string_view длины *n* имеет *n-й*элемент, индексированный числом *n* - 1.

`operator[]`быстрее, чем функция члена [для](#at) обеспечения доступа к элементам string_view.

`operator[]`не проверяет, является ли индекс, принятый в качестве аргумента, действительным. Недействительный индекс, `operator[]` передаваемый к результатам неопределенного поведения.

Возврат ссылки может быть признан недействительным, если базовые данные строки изменены или удалены объектом-владельцем.

При компиляции с [ \_иТERATOR\_\_DEBUG LEVEL,](../standard-library/iterator-debug-level.md) установленным на 1 или 2, произойдет ошибка выполнения при попытке получить доступ к элементу за пределами string_view. Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

## <a name="basic_string_viewrbegin"></a><a name="rbegin"></a>basic_string_view::rbegin

Возвращает конст-итератор к первому элементу в обратном string_view.

```cpp
constexpr const_reverse_iterator rbegin() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает итератор случайного доступа к первому элементу в обратном string_view, обращаясь к тому, что будет последним элементом в соответствующем невозвратном string_view.

### <a name="remarks"></a>Remarks

`rbegin`используется с обратным string_view так же, как [начать](#begin) используется с string_view. `rbegin`может быть использован для инициализации итерации назад.

## <a name="basic_string_viewremove_prefix"></a><a name="remove_prefix"></a>basic_string_view::remove_prefix

Перемещает указатель вперед по указанному числу элементов.

```cpp
constexpr void remove_prefix(size_type n);
```

### <a name="remarks"></a>Remarks

Оставляет базовые данные без изменений. Перемещает string_view указатель вперед на n `size` элементы и устанавливает частный элемент данных к размеру - n.

## <a name="basic_string_viewremove_suffix"></a><a name="remove_suffix"></a>basic_string_view::remove_suffix

Уменьшает размер представления на указанное количество элементов, начиная со спины.

```cpp
constexpr void remove_suffix(size_type n);
```

### <a name="remarks"></a>Remarks

Оставляет базовые данные и указатель на него без изменений. Устанавливает личный `size` член данных по размеру - n.

## <a name="basic_string_viewrend"></a><a name="rend"></a>basic_string_view::rend

Возвращает конст-итератор, который указывает на один последний элемент в обратном string_view.

```cpp
constexpr reverse_iterator rend() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Конст обратного случайного доступа итератора, который указывает на один мимо последнего элемента в обратном string_view.

### <a name="remarks"></a>Remarks

`rend`используется с обратным string_view так же, как [конец](#end) используется с string_view. `rend`может быть использован для проверки того, достиг ли обратный итератор конца своего string_view. Значение, возвращаемое `rend`, не должно быть подвергнуто удалению ссылки.

## <a name="basic_string_viewrfind"></a><a name="rfind"></a>basic_string_view::rfind

Поиск string_view в обратном направлении для подстроки, которая соответствует заданной последовательности символов.

```cpp
constexpr size_type rfind(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type rfind(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type rfind(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type rfind(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Параметры

*chVal*\
Значение символа, для которого следует искать функцию-член.

*Смещение*\
Индекс, с которого должен начаться поиск.

*Ptr*\
Строка C, для которой функция члена предназначена для поиска.

*Рассчитывать*\
Количество символов, отсчитывающих вперед от первого символа, в строке C, для которой функция участника предназначена для поиска.

*Ул*\
В string_view, для которой функция члена является поиск.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого символа подстригона при успехе; в `npos`противном случае .

## <a name="basic_string_viewsize"></a><a name="size"></a>basic_string_view::размер

Возвращает количество элементов в string_view.

```cpp
constexpr size_type size() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Длина string_view.

### <a name="remarks"></a>Remarks

String_view может изменить его длину, `remove_suffix`например, и `remove_prefix` . Поскольку это не изменяет базовые строки данных, размер string_view не обязательно является размером базовых данных.

## <a name="basic_string_viewsubstr"></a><a name="substr"></a>basic_string_view::substr

Возвращает string_view, представляющее (в лучшем случае) указанное количество символов из указанной позиции.

```cpp
constexpr basic_string_view substr(size_type offset = 0, size_type count = npos) const;
```

### <a name="parameters"></a>Параметры

*Смещение*\
Индекс, обнаруживаеший элемент в позиции, из которой сделана копия, со значением по умолчанию 0.

*Рассчитывать*\
Количество символов, которые можно включить в подстроку, если они присутствуют.

### <a name="return-value"></a>Возвращаемое значение

Объект string_view, представляющий указанную подпоследовательность элементов.

## <a name="basic_string_viewswap"></a><a name="swap"></a>basic_string_view::swap

Обменивает два string_views, другими словами указатели на базовые строки данных и значения размера.

```cpp
constexpr void swap(basic_string_view& sv) noexcept;
```

### <a name="parameters"></a>Параметры

*Sv*\
Источник string_view, чьи указатели и значения размера должны быть обменяны с указателем string_view.

## <a name="see-also"></a>См. также раздел

[\<string_view>](../standard-library/string-view.md)\
[Безопасность резьбы в стандартной библиотеке СЗ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
