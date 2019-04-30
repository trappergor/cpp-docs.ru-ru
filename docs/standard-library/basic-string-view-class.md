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
ms.openlocfilehash: 0ac5e3d528881f7b1caa0a1dcdae0161a6777e57
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346942"
---
# <a name="basicstringview-class"></a>Класс basic_string_view

Шаблон класса `basic_string_view<charT>` был добавлен в C ++ 17 для использования в качестве безопасный и эффективный способ функции принимать различные несвязанные строковые типы без функцию, имеющую для создания шаблона для этих типов. Этот класс содержит указатель-владелец непрерывная последовательность из символьных данных и длиной, указывающее количество символов в последовательности. Не предполагается, что делается по отношению к последовательности, является ли нулем.

Стандартная библиотека определяет несколько специализаций на основе типа элементов:

-  `string_view`
-  `wstring_view`
-  `u16string_view`
-  `u32string_view`

В этом документе термин «string_view» обычно относится к любой из этих определений typedef.

String_view описывает минимальные общий интерфейс, необходимые для чтения строковых данных. Он предоставляет const доступ к данным; он создает нет копии (за исключением `copy` функции). Данные могут или не может содержать значения null («\0») в любом месте. String_view не может управлять во время существования объекта. Это обязанность вызывающего, чтобы убедиться, что основные данные строки является допустимым.

Функция, которая принимает параметр типа string_view можно заставить работать с любого типа строкового типа, не делая функцию в шаблон или ограничение функцию к конкретному подмножеству строковых типов. Единственное требование заключается в том, что существует неявное преобразование из строкового типа к string_view. Все стандартные строковые типы неявно преобразуются в string_view, который содержит элементы одного типа. Другими словами `std::string` можно преобразовать в `string_view` , но не к `wstring_view`.

В следующем примере показано нешаблонную функцию `f` , принимающий параметр типа `wstring_view`. Может быть вызвана с аргументами типа `std::wstring`, `wchar_t*`, и `winrt::hstring`.

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

*CharType*<br/>
Тип символов, которые хранятся в string_view. C++ Стандартная библиотека предоставляет следующие определения типов для специализации этого шаблона.
- [string_view](../standard-library/string-view-typedefs.md#string_view) для элементов типа **char**
- [wstring_view](../standard-library/string-view-typedefs.md#wstring_view), для **wchar_t**
- [u16string_view](../standard-library/string-view-typedefs.md#u16string_view) для **char16_t**
- [u32string_view](../standard-library/string-view-typedefs.md#u32string_view) для **char32_t**.

*Признаки*<br/>
По умолчанию используется [char_traits](char-traits-struct.md)<*CharType*>.

### <a name="constructors"></a>Конструкторы

|Конструктор|Описание|
|-|-|
|[basic_string_view](#basic_string_view)|Создает string_view, который является пустым, иначе указывает полностью или частично либо другого строкового объекта данных, или массив символов C-стиля.|

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|**const_iterator**|Итератор произвольного доступа, который может читать **const** элементов.|
|**const_pointer**|`using const_pointer = const value_type*;`|
|**const_reference**|`using const_reference = const value_type&;`|
|**const_reverse_iterator**|`using const_reverse_iterator = std::reverse_iterator<const_iterator>;`|
|**difference_type**|`using difference_type = ptrdiff_t;`|
|**iterator**|`using iterator = const_iterator;`|
|**npos**|`static constexpr size_type npos = size_type(-1);`|
|**pointer**|`using pointer = value_type*;`|
|**reference**|`using reference = value_type&;`|
|**reverse_iterator**|`using reverse_iterator = const_reverse_iterator;`|
|**size_type**|`using size_type = size_t;`|
|**traits_type**|`using traits_type = Traits;`|
|**value_type**|`using value_type = CharType;`|

### <a name="member-operators"></a>Операторы-члены

|Оператор|Описание|
|-|-|
|[оператор=](#op_eq)|Назначает другой string_view string_view или можно преобразовать строковый объект.|
|[operator\[\]](#op_at)|Возвращает элемент по указанному индексу.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[at](#at)|Возвращает const_reference на элемент в указанном расположении.|
|[back](#back)|Возвращает const_reference на последний элемент.|
|[begin](#begin)|Возвращает константный итератор, адресующий первый элемент. (string_views являются неизменяемыми.)|
|[cbegin](#cbegin)|Совпадение с кодом [начать](#begin).|
|[cend](#cend)|Возвращает константный итератор, указывающий на позицию, следующую за последним элементом.|
|[copy](#copy)|Копирует не более указанное количество символов из индексированного положения в string_view источника в целевой массив символов. (Не рекомендуется. Используйте _Copy_s.)|
|[_Copy_s](#_copy_s)|Безопасные функции копирования CRT.|
|[compare](#compare)|Сравнивает string_view с указанным string_view, чтобы определить, если они равны, или если он лексикографически меньше второй.|
|[crbegin](#crbegin)|Совпадение с кодом [rbegin](#rbegin).|
|[crend](#crend)|Совпадение с кодом [rend](#rend).|
|[data](#data)|Возвращает необработанный указатель-владелец с последовательностью символов.|
|[empty](#empty)|Проверяет, является ли string_view содержит символы.|
|[end](#end)|Совпадение с кодом [cend](#cend).|
|[find](#find)|Производит поиск в прямом направлении до первого вхождения подстроки, совпадающей с заданной последовательностью символов.|
|[find_first_not_of](#find_first_not_of)|Выполняет поиск первого символа, который не является любой элемент, указанный string_view или преобразовать строковый объект.|
|[find_first_of](#find_first_of)|Выполняет поиск первого символа, совпадающего с любым элементом указанного string_view или преобразовать строковый объект.|
|[find_last_not_of](#find_last_not_of)|Выполняет поиск последнего символа, который не является любой элемент, указанный string_view или преобразовать строковый объект.|
|[find_last_of](#find_last_of)|Выполняет поиск последнего символа, который является элементом указанной string_view или преобразовать строковый объект.|
|[front](#front)|Возвращает const_reference на первый элемент.|
|[length](#length)|Возвращает текущее количество элементов.|
|[max_size](#max_size)|Возвращает максимальное число символов, которые могут содержать string_view.|
|[rbegin](#rbegin)|Возвращает константный итератор, обращающийся к первому элементу в обращенном string_view.|
|[remove_prefix](#remove_prefix)|Переместить курсор вперед на указанное число элементов.|
|[remove_suffix](#remove_suffix)|Уменьшение размера представления на указанное число элементов, начиная на обратной стороне.|
|[rend](#rend)|Возвращает константный итератор, указывающий на позицию, следующую за последним элементом в обратном string_view.|
|[rfind](#rfind)|Выполняет поиск string_view в обратном порядке для первого вхождения подстроки, совпадающей с заданной последовательностью символов.|
|[size](#size)|Возвращает текущее количество элементов.|
|[substr](#substr)|Возвращает подстроку указанной длины, начиная с указанного индекса.|
|[swap](#swap)|Местами содержимое двух string_views.|

## <a name="remarks"></a>Примечания

Если функция должна создать последовательность, длина которой превышает [max_size](#max_size) элементов, функция выдает сообщение об ошибке длины, создавая объект типа [length_error](../standard-library/length-error-class.md).

## <a name="requirements"></a>Требования

[std: c ++ 17](../build/reference/std-specify-language-standard-version.md) или более поздней версии

**Заголовок:** \<string_view >

**Пространство имен:** std

## <a name="at"></a>  basic_string_view::at

Возвращает const_reference на символ с указанным индексом от нуля.

```cpp
constexpr const_reference at(size_type offset) const;
```

### <a name="parameters"></a>Параметры

*offset*<br/>
Индекс элемента, который требуется ссылаться.

### <a name="return-value"></a>Возвращаемое значение

Const_reference символ в позиции, указанной с помощью индекса параметра.

### <a name="remarks"></a>Примечания

Первый элемент имеет индекс 0 и следующие элементы индексируются положительными целыми, таким образом, чтобы string_view длины *n* имеет *n*элемент th индексировать по номеру *n -* 1. **в** создает исключение для недопустимый индексов, в отличие от [оператор\[\]](#op_at). 

Как правило, мы рекомендуем **в** для последовательностей, такие как `std::vector` и string_view никогда не должны использоваться. Недопустимый индекс, переданный в последовательность — это логическая ошибка, должно быть для обнаружения и исправлена во время разработки. Если программа не уверены абсолютно, что его индексы являются допустимыми, его тестировать их, не вызвать at() и полагаются на исключения для защиты от неаккуратного программирования.

См. в разделе [basic_string_view::operator\[ \] ](#op_at) Дополнительные сведения.

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

## <a name="back"></a>  basic_string_view::back

Возвращает const_reference на последний элемент.

```cpp
constexpr const_reference back() const;
```

### <a name="return-value"></a>Возвращаемое значение

Const_reference на последний элемент в string_view.

### <a name="remarks"></a>Примечания

Создает исключение, если string_view пуст.

Имейте в виду, что после изменения string_view, например путем вызова `remove_suffix`, а затем элемент, возвращаемый этой функцией, больше не является последним элементом в базовых данных.

### <a name="example"></a>Пример

String_view, который создается с помощью строковом литерале отсутствует завершающий нуль-символ и, следовательно, в следующем примере `back` возвращает «p» и не «\0».

```cpp
char c[] = "Help"; // char[5]
string_view sv{ c };
cout << sv.size(); // size() == 4
cout << sv.back() << endl; // p 
```

Внедренные значения NULL рассматриваются как любой другой символ:

```cpp
string_view e = "embedded\0nulls"sv;
cout << boolalpha << (e.back() == 's'); // true
```

## <a name="basic_string_view"></a>  basic_string_view::basic_string_view

Создает string_view.

```cpp
constexpr basic_string_view() noexcept;
constexpr basic_string_view(const basic_string_view&) noexcept = default;
constexpr basic_string_view(const charT* str);
constexpr basic_string_view(const charT* str, size_type len);
```

### <a name="parameters"></a>Параметры

*str*<br/>
Указатель на необходимые символьные значения.

*функция Len*<br/>
Число символов, которые нужно включить в представление.

## <a name="remarks"></a>Примечания

Конструкторы с параметром диаграммы * предполагается, что входные данные заканчивается нулевым байтом, но завершающий нуль-символ не включается в string_view.

Можно также создать string_view с литералом. См. в разделе [оператор "" sv](string-view-operators.md#op_sv).

## <a name="begin"></a>  basic_string_view::begin

Совпадение с кодом [cbegin](#cbegin).

```cpp
constexpr const_iterator begin() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение
Возвращает const_iterator, указывающий на первый элемент.

## <a name="cbegin"></a>  basic_string_view::cbegin

Возвращает const_iterator, обращающийся к первому элементу в диапазоне.

```cpp
constexpr const_iterator cbegin() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Объект **const** итератор произвольного доступа, указывающий на первый элемент диапазона или расположение прямо за концом пустой диапазона (для пустого диапазона `cbegin() == cend()`).

## <a name="cend"></a>  basic_string_view::cend

Возвращает const_iterator, который адресует положение после последнего элемента в диапазоне.

```cpp
constexpr const_iterator cend() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Объект **const** итератор произвольного доступа, который указывает конец диапазона.

### <a name="remarks"></a>Примечания

Значение, возвращаемое `cend`, не должно быть подвергнуто удалению ссылки.

## <a name="compare"></a> basic_string_view::compare

Выполняет сравнение с учетом регистра, с указанным string_view (или можно преобразовать строковый тип), чтобы определить, если два объекта равны, или если он лексикографически меньше второй. [ \<String_view > операторы](string-view-operators.md) использовать эту функцию-член для сравнения.

```cpp
constexpr int compare(basic_string_view strv) const noexcept;
constexpr int compare(size_type pos, size_type num, basic_string_view strv) const;
constexpr int compare(size_type pos, size_type num, basic_string_view strv, size_type offset, size_type num2) const;
constexpr int compare(const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr) const;
constexpr int compare(size_type pos, size_type num, const charT* ptr, size_type num2) const;
```

### <a name="parameters"></a>Параметры

*strv*<br/>
String_view, который должен сравниваться с этой string_view.

*торговых терминалов*<br/>
Индекс этого string_view, с которого начинается сравнение.

*num*<br/>
Максимальное количество символов из этого string_view для сравнения.

*Num2*<br/>
Максимальное количество символов из *strv* для сравнения.

*offset*<br/>
Индекс *strv* с которого начинается сравнение.

*ptr*<br/>
Строка C, который требуется сравнить с этой string_view.

### <a name="return-value"></a>Возвращаемое значение

Отрицательное значение, при этом string_view меньше, чем *strv* или *ptr*; ноль, если две символьные последовательности равны; или положительное значение, если этот string_view больше, чем *strv*или *ptr*.

### <a name="remarks"></a>Примечания

`compare` Функции-члены, выполняют сравнение с учетом регистра полностью или частично каждой последовательности символов. 

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

## <a name="copy"></a>  basic_string_view::copy

Копирует не более указанное количество символов из индексированного положения в string_view источника в целевой массив символов. Мы рекомендуем использовать безопасной функции [basic_string_view::_Copy_s](#_copy_s) вместо этого.

```cpp
size_type copy(charT* ptr, size_type count, size_type offset = 0) const;
```

### <a name="parameters"></a>Параметры

*ptr*<br/>
Целевой массив символов, в который должны быть скопированы элементы.

*count*<br/>
Число копируемых символов, в основном из string_view источника.

*offset*<br/>
Начальное положение в string_view источника, из которого должны быть сделаны копии.

### <a name="return-value"></a>Возвращаемое значение

Число фактически скопированных символов.

### <a name="remarks"></a>Примечания

Символ NULL не добавляется в конец копии.

## <a name="_copy_s"></a>  basic_string_view::_Copy_s

Secure CRT функции копирования, чтобы использовать вместо [копирования](#copy).

```cpp
size_type _Copy_s(
    value_type* dest,
    size_type dest_size,
    size_type count,
    size_type _Off = 0) const;
```

### <a name="parameters"></a>Параметры

*dest*<br/>
Целевой массив символов, в который должны быть скопированы элементы.

*dest_size*<br/>
Размер *dest*.

_ *Число* число копируемых символов, в основном из исходной строки.

*_Off*<br/>
Начальная позиция в исходной строке, из которой должны быть сделаны копии.

### <a name="return-value"></a>Возвращаемое значение

Число фактически скопированных символов.

### <a name="remarks"></a>Примечания

Символ NULL не добавляется в конец копии.

 Дополнительные сведения см. в разделе [c-runtime-library/security-features-in-the-crt](../c-runtime-library/security-features-in-the-crt.md).

## <a name="crbegin"></a>  basic_string_view::crbegin

Возвращает const_reverse_iterator, обращающийся к первому элементу в обращенном string_view.

```cpp
constexpr const_reverse_iterator crbegin() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Const_reverse_iterator, обращающийся к первому элементу в обращенном string_view. 

## <a name="crend"></a>  basic_string_view::crend

Совпадение с кодом [rend](#rend). 

```cpp
constexpr const_reverse_iterator crend() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает const_reverse_iterator, который отвечает на одну позицию после конца обратном string_view.

## <a name="data"></a>  basic_string_view::data

Возвращает необработанный указатель-владелец объекта, который использовался для создания string_view const последовательность символов.

```cpp
constexpr value_type *data() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Указатель к const на первый элемент последовательности символов.

### <a name="remarks"></a>Примечания

Указатель не может изменить символы.

Последовательность символов string_view не обязательно нулем. Тип возвращаемого значения для `data` не допустимую строку C, так как нуль-символ возвращает добавляется. Символ null '\0' не имеет специального значения в объекте типа string_view и может быть частью объекта string_view так же, как и любой другой символ.

## <a name="empty"></a>  basic_string_view::empty

Проверяет, является ли string_view содержит символы, или нет.

```cpp
constexpr bool empty() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если string_view объект не содержит символов; **false** Если у него есть хотя бы один символ.

### <a name="remarks"></a>Примечания

Функция-член эквивалентно [размер](#size)() == 0.

## <a name="end"></a>  basic_string_view::end

Возвращает const_iterator произвольного доступа, указывающий на позицию, следующую за последним элементом.

```cpp
constexpr const_iterator end() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает const_iterator произвольного доступа, указывающий на позицию, следующую за последним элементом.

### <a name="remarks"></a>Примечания

`end` используется для проверки const_iterator достиг конца его string_view ли. Значение, возвращаемое `end`, не должно быть подвергнуто удалению ссылки.

## <a name="find"></a>  basic_string_view::find

Выполняет поиск string_view в прямом направлении до первого вхождения символа или подстроки, совпадающей с заданной последовательностью символов.

```cpp
constexpr size_type find(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>Параметры

*str*<br/>
String_view, для которого является функция-член, для поиска.

*chVal*<br/>
Значение символа, для которого следует искать функцию-член.

*offset*<br/>
Индекс, по которому начинается поиск.

*ptr*<br/>
Строка C, для которого является функция-член, для поиска.

*count*<br/>
Число символов в *ptr*, начиная с первого символа.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого символа искомой подстроки, если она успешно найдена; в противном случае — `npos`.

## <a name="find_first_not_of"></a>  basic_string_view::find_first_not_of

Выполняет поиск первого символа, который не является элементом указанной string_view или преобразовать строковый объект.

```cpp
constexpr size_type find_first_not_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_first_not_of(const charT* ptr, size_type offset = 0) const;
```

### <a name="parameters"></a>Параметры

*str*<br/>
String_view, для которого является функция-член, для поиска.

*chVal*<br/>
Значение символа, для которого следует искать функцию-член.

*offset*<br/>
Индекс, по которому начинается поиск.

*ptr*<br/>
Строка C, для которого является функция-член, для поиска.

*count*<br/>
Число символов, начиная с первого символа в строке C, для которого является функция-член, для поиска.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого символа искомой подстроки, если она успешно найдена; в противном случае — `npos`.

## <a name="find_first_of"></a>  basic_string_view::find_first_of

Выполняет поиск первого символа, совпадающего с любым элементом указанного string_view.

```cpp
constexpr size_type find_first_of(basic_string_view str, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(charT chVal, size_type offset = 0) const noexcept;
constexpr size_type find_first_of(const charT* str, size_type offset, size_type count) const;
constexpr size_type find_first_of(const charT* str, size_type offset = 0) const;
```

### <a name="parameters"></a>Параметры

*chVal*<br/>
Значение символа, для которого следует искать функцию-член.

*offset*<br/>
Индекс, по которому начинается поиск.

*ptr*<br/>
Строка C, для которого является функция-член, для поиска.

*count*<br/>
Число символов, начиная с первого символа в строке C, для которого является функция-член, для поиска.

*str*<br/>
String_view, для которого является функция-член, для поиска.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого символа искомой подстроки, если она успешно найдена; в противном случае — `npos`.

## <a name="find_last_not_of"></a>  basic_string_view::find_last_not_of

Выполняет поиск последнего символа, который не является ни с одним элементом заданного string_view.

```cpp
constexpr size_type find_last_not_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_not_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Параметры

*str*<br/>
String_view, для которого является функция-член, для поиска.

*chVal*<br/>
Значение символа, для которого следует искать функцию-член.

*offset*<br/>
Индекс, по которому поиск до конца.

*ptr*<br/>
Строка C, для которого является функция-член, для поиска.

*count*<br/>
Число символов, начиная с первого символа в *ptr*.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого символа искомой подстроки, если она успешно найдена; в противном случае — `string_view::npos`.

## <a name="find_last_of"></a>  basic_string_view::find_last_of

Выполняет поиск последнего символа, совпадающего с любым элементом указанного string_view.

```cpp
constexpr size_type find_last_of(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type find_last_of(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type find_last_of(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Параметры

*str*<br/>
String_view, для которого является функция-член, для поиска.

*chVal*<br/>
Значение символа, для которого следует искать функцию-член.

*offset*<br/>
Индекс, по которому поиск до конца.

*ptr*<br/>
Строка C, для которого является функция-член, для поиска.

*count*<br/>
Число символов, начиная с первого символа в строке C, для которого является функция-член, для поиска.

### <a name="return-value"></a>Возвращаемое значение

Индекс последнего символа искомой подстроки, если он был успешно найден; в противном случае — `npos`.

## <a name="front"></a>  basic_string_view::front

Возвращает const_reference на первый элемент.

```cpp
constexpr const_reference front() const;
```

### <a name="return-value"></a>Возвращаемое значение

Const_reference на первый элемент.

### <a name="remarks"></a>Примечания

Создает исключение, если string_view пуст.

## <a name="length"></a> basic_string_view::length

Возвращает текущее количество элементов.

```cpp
constexpr size_type length() const noexcept;
```

### <a name="remarks"></a>Примечания

Функция-член такая же, как [size](#size).

## <a name="max_size"></a>  basic_string_view::max_size

Возвращает максимальное число символов, которые может содержать string_view.

```cpp
constexpr size_type max_size() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Максимальное число символов, которое string_view может содержать.

### <a name="remarks"></a>Примечания

Исключение типа [length_error](../standard-library/length-error-class.md) возникает, когда операция формирует string_view с длиной, превышающей `max_size()`.

## <a name="op_eq"></a>  basic_string_view::operator=

Назначает другой string_view string_view или можно преобразовать строковый объект.

```cpp
constexpr basic_string_view& operator=(const basic_string_view&) noexcept = default;
```
### <a name="example"></a>Пример

```cpp
   string_view s = "Hello";
   string_view s2 = s;
```
## <a name="op_at"></a>  basic_string_view::operator[]

Предоставляет const_reference на символ с указанным индексом.

```cpp
constexpr const_reference operator[](size_type offset) const;
```

### <a name="parameters"></a>Параметры

*offset*<br/>
Индекс элемента, который требуется ссылаться.

### <a name="return-value"></a>Возвращаемое значение

Const_reference символ в позиции, указанной с помощью индекса параметра.

### <a name="remarks"></a>Примечания

Первый элемент имеет индекс 0, а также следующие элементы индексируются положительными целыми, таким образом, чтобы string_view длины *n* имеет *n*элемент th индексировать по номеру *n* - 1.

`operator[]` выполняется быстрее, чем функция-член [в](#at) за предоставление доступ на чтение к элементам string_view.

`operator[]` не проверяет допустимость индекса, передается в качестве аргумента. Недопустимый индекс, переданный для `operator[]` приводит к неопределенному поведению.

Возвращаемая ссылка может стать недействительной, если основные данные строки изменяются или удаляются, объект-владелец.

При компиляции с параметром [ \_ИТЕРАТОР\_Отладка\_уровень](../standard-library/iterator-debug-level.md) значение 1 или 2, возникнет ошибка времени выполнения при попытке доступа к элементу за пределами string_view. Для получения дополнительной информации см. [Checked Iterators](../standard-library/checked-iterators.md).

## <a name="rbegin"></a>  basic_string_view::rbegin

Возвращает константный итератор на первый элемент в обратном string_view.

```cpp
constexpr const_reverse_iterator rbegin() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает итератор произвольного доступа, на первый элемент в обратном string_view, адресация бы последним элементом в соответствующей необращенной string_view.

### <a name="remarks"></a>Примечания

`rbegin` используется с обратным string_view так же, как [начать](#begin) используется с string_view. `rbegin` можно использовать для инициализации итерации в обратном направлении.

## <a name="remove_prefix"></a> basic_string_view::remove_prefix

Переместить курсор вперед на указанное число элементов.

```cpp
constexpr void remove_prefix(size_type n);
```

### <a name="remarks"></a>Примечания

Оставляет без изменений базовых данных. Перемещает указатель string_view вперед по n элементов и задает закрытый `size` элемент данных до размера - n.

## <a name="remove_suffix"></a> basic_string_view::remove_suffix

Уменьшение размера представления на указанное число элементов, начиная на обратной стороне.

```cpp
constexpr void remove_suffix(size_type n);
```

### <a name="remarks"></a>Примечания

Оставляет базовых данных и указатель без изменений. Задает закрытый `size` элемент данных до размера - n.

## <a name="rend"></a>  basic_string_view::rend

Возвращает константный итератор, указывающий на позицию, следующую за последним элементом в обратном string_view.

```cpp
constexpr reverse_iterator rend() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Константный Обратный итератор произвольного доступа, указывающий на позицию, следующую за последним элементом в обратном string_view.

### <a name="remarks"></a>Примечания

`rend` используется с обратным string_view так же, как [окончания](#end) используется с string_view. `rend` можно использовать для тестирования обратного достиг ли итератор конца своего string_view. Значение, возвращаемое `rend`, не должно быть подвергнуто удалению ссылки.

## <a name="rfind"></a>  basic_string_view::rfind

Выполняет поиск string_view в обратном порядке для подстроки, совпадающей с заданной последовательностью символов.

```cpp
constexpr size_type rfind(basic_string_view str, size_type offset = npos) const noexcept;
constexpr size_type rfind(charT chVal, size_type offset = npos) const noexcept;
constexpr size_type rfind(const charT* ptr, size_type offset, size_type count) const;
constexpr size_type rfind(const charT* ptr, size_type offset = npos) const;
```

### <a name="parameters"></a>Параметры

*chVal*<br/>
Значение символа, для которого следует искать функцию-член.

*offset*<br/>
Индекс, по которому начинается поиск.

*ptr*<br/>
Строка C, для которого является функция-член, для поиска.

*count*<br/>
Число символов, начиная с первого символа в строке C, для которого является функция-член, для поиска.

*str*<br/>
String_view, для которого является функция-член, для поиска.

### <a name="return-value"></a>Возвращаемое значение

Индекс первого символа подстроки при успешном выполнении; в противном случае `npos`.

## <a name="size"></a>  basic_string_view::size

Возвращает количество элементов в string_view.

```cpp
constexpr size_type size() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Длина string_view.

### <a name="remarks"></a>Примечания

String_view можно изменить его длиной, например, `remove_prefix` и `remove_suffix`. Так как это не изменять основные данные строки, размер string_view не обязательно размер базовых данных.

## <a name="substr"></a>  basic_string_view::substr

Возвращает string_view, представляющий (максимум) указанное количество символов из указанной позиции.

```cpp
constexpr basic_string_view substr(size_type offset = 0, size_type count = npos) const;
```

### <a name="parameters"></a>Параметры

*offset*<br/>
Индекс поиска элемента в позиции, из которого делается копия, со значением по умолчанию 0.

*count*<br/>
Число знаков в подстроке, если они присутствуют.

### <a name="return-value"></a>Возвращаемое значение

Объект string_view, представляющий указанный вложенный последовательность элементов.

## <a name="swap"></a>  basic_string_view::swap

Меняет местами два string_views, другими словами указатели основные данные строки и размер.

```cpp
constexpr void swap(basic_string_view& sv) noexcept;
```

### <a name="parameters"></a>Параметры

*sv*<br/>
String_view источника, которого указатель и размеры значений, обмен которыми происходит с данными о string_view назначения.

## <a name="see-also"></a>См. также

[\<string_view >](../standard-library/string-view.md)<br/>
[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
