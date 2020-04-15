---
title: Операторы &lt;string&gt;
ms.date: 11/04/2016
f1_keywords:
- string/std::operator!=
- string/std::operator&gt;
- string/std::operator&gt;&gt;
- string/std::operator&gt;=
- string/std::operator&lt;
- string/std::operator&lt;&lt;
- string/std::operator&lt;=
- string/std::operator+
- string/std::operator==
ms.assetid: 33ce8f05-06c7-45d3-a0cb-bcd27cf93910
helpviewer_keywords:
- std::operator!= (string)
- std::operator&gt; (string)
- std::operator&gt;&gt; (string)
- std::operator&gt;= (string)
- std::operator&lt; (string)
- std::operator&lt;&lt; (string)
- std::operator&lt;= (string), std::operator== (string)
ms.openlocfilehash: fef2eb784eca9c9eabbdcd727b051d5c2a4ccfd2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376653"
---
# <a name="ltstringgt-operators"></a>Операторы &lt;string&gt;

||||
|-|-|-|
|[оператора!](#op_neq)|[Оператор&gt;](#op_gt)|[Оператор&gt;&gt;](#op_gt_gt)|
|[Оператор&gt;=](#op_gt_eq)|[Оператор&lt;](#op_lt)|[Оператор&lt;&lt;](#op_lt_lt)|
|[Оператор&lt;=](#op_lt_eq)|[оператор](#op_add)|[оператора](#op_eq_eq)|

## <a name="operator"></a><a name="op_add"></a>оператор

Сцепляет два строковых объекта.

```cpp
template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator> operator+(
    const CharType left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const basic_string<CharType, Traits, Allocator>&& left,
    CharType right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>&& right);

template <class CharType, class Traits, class Allocator>
basic_string<CharType, Traits, Allocator>&& operator+(
    CharType left,
    const basic_string<CharType, Traits, Allocator>&& right);
```

### <a name="parameters"></a>Параметры

*Левой*\
Строка в стиле C или объект типа `basic_string` для объединения.

*Правильно*\
Строка в стиле C или объект типа `basic_string` для объединения.

### <a name="return-value"></a>Возвращаемое значение

Строка, которая является объединением входных строк.

### <a name="remarks"></a>Remarks

Функции, каждая из которых перегружается, `operator+` чтобы совмещеть два объекта шаблона класса basic_string [класса.](../standard-library/basic-string-class.md) Все эффективно `basic_string< CharType, Traits, Allocator>(Left).append(right)`вернуться . Для получения дополнительной [append](../standard-library/basic-string-class.md#append)информации см.

### <a name="example"></a>Пример

```cpp
// string_op_con.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an object of type basic_string<char>
   string s1 ( "anti" );
   string s2 ( "gravity" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "heroine";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // Declaring a character constant
   char c1 = '!';
   cout << "The character constant c1 = " << c1 << "." << endl;

   // First member function: concatenates an  object
   // of type basic_string with an object of type basic_string
   string s12 = s1 + s2;
   cout << "The string concatenating s1 & s2 is: " << s12 << endl;

   // Second & fourth member functions: concatenate an object
   // of type basic_string with an object of C-syle string type
   string s1s3 = s1 + s3;
   cout << "The string concatenating s1 & s3 is: " << s1s3 << endl;

   // Third & fifth member functions: concatenate an object
   // of type basic_string with a character constant
   string s1s3c1 = s1s3 + c1;
   cout << "The string concatenating s1 & s3 is: " << s1s3c1 << endl;
}
```

```Output
The basic_string s1 = anti.
The basic_string s2 = gravity.
The C-style string s3 = heroine.
The character constant c1 = !.
The string concatenating s1 & s2 is: antigravity
The string concatenating s1 & s3 is: antiheroine
The string concatenating s1 & s3 is: antiheroine!
```

## <a name="operator"></a><a name="op_neq"></a>оператора!

Проверяет, что строковый объект слева от оператора не равен строковому объекту справа от оператора. 

```cpp
template <class CharType, class Traits, class Allocator>
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator!=(
    const basic_string<CharType, Traits, Allocator>& left,
const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator!=(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Левой*\
Строка в стиле C или объект типа `basic_string` для сравнения.

*Правильно*\
Строка в стиле C или объект типа `basic_string` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если строковый объект в левой части оператора лексикографически не равен строковому объекту в правой части; в противном случае — значение **false**.

### <a name="remarks"></a>Remarks

Сравнение между объектами строк основывается на попарном лексикографическом сравнении их символов. Две строки считаются равными, если они имеют одинаковое число символов и их соответствующие значения символов совпадают. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// string_op_ne.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "pluck" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "pluck";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 != s2 )
      cout << "The strings s1 & s2 are not equal." << endl;
   else
      cout << "The strings s1 & s2 are equal." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s1 != s3 )
      cout << "The strings s1 & s3 are not equal." << endl;
   else
      cout << "The strings s1 & s3 are equal." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s3 != s2 )
      cout << "The strings s3 & s2 are not equal." << endl;
   else
      cout << "The strings s3 & s2 are equal." << endl;
}
```

```Output
The basic_string s1 = pluck.
The basic_string s2 = strum.
The C-style string s3 = pluck.
The strings s1 & s2 are not equal.
The strings s1 & s3 are equal.
The strings s3 & s2 are not equal.
```

## <a name="operator"></a><a name="op_eq_eq"></a>оператора

Проверяет, равен ли строковый объект слева от оператора строковому объекту справа от оператора.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator==(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator==(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Левой*\
Строка в стиле C или объект типа `basic_string` для сравнения.

*Правильно*\
Строка в стиле C или объект типа `basic_string` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если строковый объект в левой части оператора лексикографически равен строковому объекту в правой части; в противном случае — значение **false**.

### <a name="remarks"></a>Remarks

Сравнение между объектами строк основывается на попарном лексикографическом сравнении их символов. Две строки считаются равными, если они имеют одинаковое число символов и их соответствующие значения символов совпадают. В противном случае они не равны.

### <a name="example"></a>Пример

```cpp
// string_op_eq.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "pluck" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "pluck";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 == s2 )
      cout << "The strings s1 & s2 are equal." << endl;
   else
      cout << "The strings s1 & s2 are not equal." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s1 == s3 )
      cout << "The strings s1 & s3 are equal." << endl;
   else
      cout << "The strings s1 & s3 are not equal." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s3 == s2 )
      cout << "The strings s3 & s2 are equal." << endl;
   else
      cout << "The strings s3 & s2 are not equal." << endl;
}
```

```Output
The basic_string s1 = pluck.
The basic_string s2 = strum.
The C-style string s3 = pluck.
The strings s1 & s2 are not equal.
The strings s1 & s3 are equal.
The strings s3 & s2 are not equal.
```

## <a name="operatorlt"></a><a name="op_lt"></a>Оператор&lt;

Проверяет, что строковый объект слева от оператора меньше строкового объекта справа от оператора.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator<(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator<(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Левой*\
Строка в стиле C или объект типа `basic_string` для сравнения.

*Правильно*\
Строка в стиле C или объект типа `basic_string` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если строковый объект в левой части оператора лексикографически меньше, чем строковый объект в правой части; в противном случае — значение **false**.

### <a name="remarks"></a>Remarks

Лексикографическое сравнение между строками сравнивает их символ за символом до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, поэтому сроки равны.

### <a name="example"></a>Пример

```cpp
// string_op_lt.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "strict";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 < s2 )
      cout << "The string s1 is less than the string s2." << endl;
   else
      cout << "The string s1 is not less than the string s2." << endl;

   // Second member function: comparison between left-hand object
   // of type basic_string & right-hand object of C-syle string type
   if ( s1 < s3 )
      cout << "The string s1 is less than the string s3." << endl;
   else
      cout << "The string s1 is not less than the string s3." << endl;

   // Third member function: comparison between left-hand object
   // of C-syle string type & right-hand object of type basic_string
   if ( s3 < s2 )
      cout << "The string s3 is less than the string s2." << endl;
   else
      cout << "The string s3 is not less than the string s2." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = strict.
The string s1 is less than the string s2.
The string s1 is not less than the string s3.
The string s3 is less than the string s2.
```

## <a name="operatorlt"></a><a name="op_lt_eq"></a>Оператор&lt;=

Проверяет, что строковый объект слева от оператора меньше или равен строковому объекту справа от оператора.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator<=(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator<=(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Левой*\
Строка в стиле C или объект типа `basic_string` для сравнения.

*Правильно*\
Строка в стиле C или объект типа `basic_string` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если строковый объект в левой части оператора лексикографически меньше, чем строковый объект в правой части, или равен ему; в противном случае — значение **false**.

### <a name="remarks"></a>Remarks

Лексикографическое сравнение между строками сравнивает их символ за символом до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, и поэтому сроки равны.

### <a name="example"></a>Пример

```cpp
// string_op_le.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "strict";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 <= s2 )
      cout << "The string s1 is less than or equal to "
           << "the string s2." << endl;
   else
      cout << "The string s1 is greater than "
           << "the string s2." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s1 <= s3 )
      cout << "The string s1 is less than or equal to "
           << "the string s3." << endl;
   else
      cout << "The string s1 is greater than "
           << "the string s3." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type  & right-side object of type basic_string
   if ( s2 <= s3 )
      cout << "The string s2 is less than or equal to "
           << "the string s3." << endl;
   else
      cout << "The string s2 is greater than "
           << "the string s3." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = strict.
The string s1 is less than or equal to the string s2.
The string s1 is less than or equal to the string s3.
The string s2 is greater than the string s3.
```

## <a name="operatorltlt"></a><a name="op_lt_lt"></a>Оператор&lt;&lt;

Функция шаблона, записывающая строку в выходной поток.

```cpp
template <class CharType, class Traits, class Allocator>
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& _Ostr,
    const basic_string<CharType, Traits, Allocator>& str);
```

### <a name="parameters"></a>Параметры

*_ostr*\
Поток вывода, в который выполняется запись.

*Ул*\
Строка, которую необходимо ввести в поток вывода.

### <a name="return-value"></a>Возвращаемое значение

Записывает значение указанной строки в поток вывода *_Ostr.*

### <a name="remarks"></a>Remarks

Функция шаблона перегружает **оператора<<** вставить *объектную стрядку* шаблона класса [basic_string](../standard-library/basic-string-class.md) в поток * \_Ostr.* Функция эффективно `_Ostr.write( str.c_str, str.size )`возвращается.

## <a name="operatorgt"></a><a name="op_gt"></a>Оператор&gt;

Проверяет, что строковый объект слева от оператора больше строкового объекта справа от оператора.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator>(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator>(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Левой*\
Строка в стиле C или объект типа `basic_string` для сравнения.

*Правильно*\
Строка в стиле C или объект типа `basic_string` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если строковый объект в левой части оператора лексикографически больше, чем строковый объект в правой части; в противном случае — значение **false**.

### <a name="remarks"></a>Remarks

Лексикографическое сравнение между строками сравнивает их символ за символом до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, поэтому сроки равны.

### <a name="example"></a>Пример

```cpp
// string_op_gt.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "stricture";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 > s2 )
      cout << "The string s1 is greater than "
           << "the string s2." << endl;
   else
      cout << "The string s1 is not greater than "
           << "the string s2." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s3 > s1 )
      cout << "The string s3 is greater than "
           << "the string s1." << endl;
   else
      cout << "The string s3 is not greater than "
           << "the string s1." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s2 > s3 )
      cout << "The string s2 is greater than "
           << "the string s3." << endl;
   else
      cout << "The string s2 is not greater than "
           << "the string s3." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = stricture.
The string s1 is not greater than the string s2.
The string s3 is greater than the string s1.
The string s2 is greater than the string s3.
```

## <a name="operatorgt"></a><a name="op_gt_eq"></a>Оператор&gt;=

Проверяет, что строковый объект слева от оператора больше или равен строковому объекту справа от оператора.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right);

template <class CharType, class Traits, class Allocator>
bool operator>=(
    const basic_string<CharType, Traits, Allocator>& left,
    const CharType* right);

template <class CharType, class Traits, class Allocator>
bool operator>=(
    const CharType* left,
    const basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*Левой*\
Строка в стиле C или объект типа `basic_string` для сравнения.

*Правильно*\
Строка в стиле C или объект типа `basic_string` для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если строковый объект в левой части оператора лексикографически больше, чем строковый объект в правой части, или равен ему; в противном случае — значение **false**.

### <a name="remarks"></a>Remarks

Лексикографическое сравнение между строками сравнивает их символ за символом до:

- Находит два соответствующих символа, которые считаются неравными, а результат их сравнения считается результатом сравнения строк.

- Неравенство не обнаруживается, однако одна строка содержит больше символов, чем другая, и более короткая строка считается меньше, чем более длинная.

- Неравенство не обнаруживается, и считается, что строки содержат одинаковое количество символов, поэтому сроки равны.

### <a name="example"></a>Пример

```cpp
// string_op_ge.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // Declaring an objects of type basic_string<char>
   string s1 ( "strict" );
   string s2 ( "strum" );
   cout << "The basic_string s1 = " << s1 << "." << endl;
   cout << "The basic_string s2 = " << s2 << "." << endl;

   // Declaring a C-style string
   char *s3 = "stricture";
   cout << "The C-style string s3 = " << s3 << "." << endl;

   // First member function: comparison between left-side object
   // of type basic_string & right-side object of type basic_string
   if ( s1 >= s2 )
      cout << "The string s1 is greater than or equal to "
           << "the string s2." << endl;
   else
      cout << "The string s1 is less than "
           << "the string s2." << endl;

   // Second member function: comparison between left-side object
   // of type basic_string & right-side object of C-syle string type
   if ( s3 >= s1 )
      cout << "The string s3 is greater than or equal to "
           << "the string s1." << endl;
   else
      cout << "The string s3 is less than "
           << "the string s1." << endl;

   // Third member function: comparison between left-side object
   // of C-syle string type & right-side object of type basic_string
   if ( s2 >= s3 )
      cout << "The string s2 is greater than or equal to "
           << "the string s3." << endl;
   else
      cout << "The string s2 is less than "
           << "the string s3." << endl;
}
```

```Output
The basic_string s1 = strict.
The basic_string s2 = strum.
The C-style string s3 = stricture.
The string s1 is less than the string s2.
The string s3 is greater than or equal to the string s1.
The string s2 is greater than or equal to the string s3.
```

## <a name="operatorgtgt"></a><a name="op_gt_gt"></a>Оператор&gt;&gt;

Функция-шаблон, считывающая строку из входного потока.

```cpp
template <class CharType, class Traits, class Allocator>
basic_istream<CharType, Traits>& operator>>(
    basic_istream<CharType, Traits>& _Istr,
    basic_string<CharType, Traits, Allocator>& right);
```

### <a name="parameters"></a>Параметры

*_istr*\
Входной поток, используемый для извлечения последовательности

*Правильно*\
Строка, извлекаемая из входного потока.

### <a name="return-value"></a>Возвращаемое значение

Читает значение указанной строки из *_Istr* и возвращает ее *вправо.*

### <a name="remarks"></a>Remarks

Оператор пропускает начальные пробелы, если не установлен флаг `skipws`. Он считывает следующие символы до пробела или до конца файла.

Функция шаблона перегружает **оператора>>** заменить управляемую *правой* последовательностью элементы, извлеченные из ручья *_Istr.* Точки остановки извлечения:

- в конце файла;

- После извлечения `_Istr` функцией. Элементы **width**, если это значение ненулевое.

После извлечения `_Istr` функцией. Элементы [max_size](../standard-library/basic-string-class.md#max_size).

- После того как функция извлечет элемент *ch*, для которого [use_facet](../standard-library/basic-filebuf-class.md#open)< **ctype**\< **CharType**> >( `getloc`). **is**( **ctype**\< **CharType**>:: **space**, *ch*) имеет значение true (в этом случае символ возвращается).

Если функция не извлекает элементов,`ios_base::failbit`она вызывает [setstate](../standard-library/basic-ios-class.md#setstate)(). В любом случае она вызывает **istr**. **width**(0) и возвращает \* **this**.

### <a name="example"></a>Пример

```cpp
// string_op_read_.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   string c0;
   cout << "Input a string c0 ( try: Fibonacci numbers ): ";
   cin >> c0;
   cout << "The string entered is c0 = " << c0 << endl;
}
```

## <a name="see-also"></a>См. также раздел

[\<струнная>](../standard-library/string.md)
