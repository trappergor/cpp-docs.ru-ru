---
title: Структура char_traits
ms.date: 05/07/2019
f1_keywords:
- iosfwd/std::char_traits
- iosfwd/std::char_traits::char_type
- iosfwd/std::char_traits::int_type
- iosfwd/std::char_traits::off_type
- iosfwd/std::char_traits::pos_type
- iosfwd/std::char_traits::state_type
- iosfwd/std::char_traits::assign
- iosfwd/std::char_traits::compare
- iosfwd/std::char_traits::copy
- iosfwd/std::char_traits::_Copy_s
- iosfwd/std::char_traits::eof
- iosfwd/std::char_traits::eq
- iosfwd/std::char_traits::eq_int_type
- iosfwd/std::char_traits::find
- iosfwd/std::char_traits::length
- iosfwd/std::char_traits::lt
- iosfwd/std::char_traits::move
- iosfwd/std::char_traits::_Move_s
- iosfwd/std::char_traits::not_eof
- iosfwd/std::char_traits::to_char_type
- iosfwd/std::char_traits::to_int_type
helpviewer_keywords:
- char_traits struct
- char_traits class
ms.assetid: 568e59f0-4521-4207-9223-9dcf6a16d620
ms.openlocfilehash: 541f468071e315b205abb8f7b9c865f045c510fe
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220524"
---
# <a name="chartraits-struct"></a>Структура char_traits

Структура char_traits описывает атрибуты, связанные с символом.

## <a name="syntax"></a>Синтаксис

```cpp
template <class CharType>
struct char_traits;
```

### <a name="parameters"></a>Параметры

*CharType*<br/>
Тип данных элемента.

## <a name="remarks"></a>Примечания

Структура шаблона описывает различные признаки символов для типа `CharType`. Класс шаблона [basic_string](../standard-library/basic-string-class.md) а также несколько классов шаблонов iostream, включая [basic_ios](../standard-library/basic-ios-class.md), использовать эту информацию для управления элементами типа `CharType`. Для такого типа элемента не требуются явное создание или уничтожение. Он должен предоставлять конструктор по умолчанию, конструктор копирования и оператор присваивания с ожидаемой семантикой. Побитовое копирование должно иметь такой же эффект, как и присваивание. Ни одна из функций — членов структуры char_traits не может создавать исключения.

### <a name="typedefs"></a>Определения типов

|Имя типа|Описание|
|-|-|
|[char_type](#char_type)|Тип символа.|
|[int_type](#int_type)|Целочисленный тип, который может представлять символ типа `char_type` или символ конца файла (EOF).|
|[off_type](#off_type)|Целочисленный тип, который может представлять смещения между позициями в потоке.|
|[pos_type](#pos_type)|Целочисленный тип, который может представлять позиции в потоке.|
|[state_type](#state_type)|Тип, представляющий состояние преобразования в многобайтовые символы в потоке.|

### <a name="member-functions"></a>Функции-члены

|Функция-член|Описание|
|-|-|
|[assign](#assign)|Присваивает значение одного символа другому.|
|[compare](#compare)|Сравнивает указанное количество символов в двух строках.|
|[copy](#copy)|Копирует указанное количество символов из одной строки в другую. Не рекомендуется. Вместо этой функции используйте [char_traits::_Copy_s](#copy_s).|
|[_Copy_s](#copy_s)|Копирует указанное количество символов из одной строки в другую.|
|[eof](#eof)|Возвращает символ конца файла (EOF).|
|[eq](#eq)|Проверяет два символа `char_type` на равенство.|
|[eq_int_type](#eq_int_type)|Проверяет два символа, представленные как `int_type`, на равенство.|
|[find](#find)|Выполняет поиск первого вхождения указанного символа в диапазоне символов.|
|[length](#length)|Возвращает длину строки.|
|[lt](#lt)|Проверяет, меньше ли один символ другого.|
|[move](#move)|Копирует указанное количество символов в последовательности в другую, возможно, перекрывающуюся, последовательность. Не рекомендуется. Вместо этой функции используйте [char_traits::_Move_s](#move_s).|
|[_Move_s](#move_s)|Копирует указанное количество символов в последовательности в другую, возможно, перекрывающуюся, последовательность.|
|[not_eof](#not_eof)|Проверяет, является ли символ символом конца файла (EOF).|
|[to_char_type](#to_char_type)|Преобразует символ `int_type` в соответствующий символ `char_type` и возвращает результат.|
|[to_int_type](#to_int_type)|Преобразует символ `char_type` в соответствующий символ `int_type` и возвращает результат.|

## <a name="requirements"></a>Требования

**Заголовок:** \<string>

**Пространство имен:** std

## <a name="assign"></a>  char_traits::assign

Присваивает значение одного символа другому элементу или диапазону элементов в строке.

```cpp
static void assign(char_type& _CharTo,
    const char_type& _CharFrom);

static char_type *assign(char_type* strTo,
    size_t _Num,
    char_type _CharFrom);
```

### <a name="parameters"></a>Параметры

**_** *CharFrom* знак, значение которого равно для назначения.

*_CharTo*<br/>
Элемент, которому должно быть присвоено это значение символа.

*strTo*<br/>
Строка или массив символов, чьим начальным элементам должны присваиваться значения символов.

*_Num*<br/>
Число элементов, которым будут назначаться значения.

### <a name="return-value"></a>Возвращаемое значение

Вторая функция-член возвращает указатель на строку, первым *_Num* элементы были назначены значения *_CharFrom*.

### <a name="example"></a>Пример

```cpp
// char_traits_assign.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   // The first member function assigning
   // one character value to another character
   char ChTo = 't';
   const char ChFrom = 'f';
   cout << "The initial characters ( ChTo , ChFrom ) are: ( "
        << ChTo << " , " << ChFrom << " )." << endl;
   char_traits<char>::assign ( ChTo , ChFrom );
   cout << "After assigning, the characters ( ChTo , ChFrom ) are: ( "
        << ChTo << " , " << ChFrom << " )." << endl << endl;

   // The second member function assigning
   // character values to initial part of a string
   char_traits<char>::char_type s1[] = "abcd-1234-abcd";
   char_traits<char>::char_type* result1;
   cout << "The target string s1 is: " << s1 << endl;
   result1 = char_traits<char>::assign ( s1 , 4 , 'f' );
   cout << "The result1 = assign ( s1 , 4 , 'f' ) is: "
        << result1 << endl;
}
```

```Output
The initial characters ( ChTo , ChFrom ) are: ( t , f ).
After assigning, the characters ( ChTo , ChFrom ) are: ( f , f ).

The target string s1 is: abcd-1234-abcd
The result1 = assign ( s1 , 4 , 'f' ) is: ffff-1234-abcd
```

## <a name="char_type"></a>  char_traits::char_type

Тип символа.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Примечания

Этот тип является синонимом для параметра шаблона `CharType`.

### <a name="example"></a>Пример

Пример объявления и использования `char_type` см. в примере для [copy](#copy).

## <a name="compare"></a>  char_traits::compare

Сравнивает указанное количество символов в двух строках.

```cpp
static int compare(const char_type* str1,
    const char_type* str2,
    size_t _Num);
```

### <a name="parameters"></a>Параметры

*str1*<br/>
Первая из двух строк для сравнения друг с другом.

*str2*<br/>
Вторая из двух строк для сравнения друг с другом.

*_Num*<br/>
Число элементов в строках для сравнения.

### <a name="return-value"></a>Возвращаемое значение

Отрицательное значение, если первая строка меньше второй строки; 0, если две строки равны; или положительное значение, если первая строка больше второй.

### <a name="remarks"></a>Примечания

Строки сравниваются поэлементно; сначала выполняется проверка на равенство, и если два соответствующих элемента в последовательных тестах оказываются не равны, то затем проверяется, кто из них меньше.

Если две строки считаются равными в рамках диапазона, но одна строка длиннее другой, то более короткая строка меньше, чем более длинная.

### <a name="example"></a>Пример

```cpp
// char_traits_compare.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main() {
   using namespace std;

   char_traits<char>::char_type* s1 = "CAB";
   char_traits<char>::char_type* s2 = "ABC";
   char_traits<char>::char_type* s3 = "ABC";
   char_traits<char>::char_type* s4 = "ABCD";

   cout << "The string s1 is: " << s1 << endl;
   cout << "The string s2 is: " << s2 << endl;
   cout << "The string s3 is: " << s3 << endl;
   cout << "The string s4 is: " << s4 << endl;

   int comp1, comp2, comp3, comp4;
   comp1 = char_traits<char>::compare ( s1 , s2 , 2 );
   comp2 = char_traits<char>::compare ( s2 , s3 , 3 );
   comp3 = char_traits<char>::compare ( s3 , s4 , 4 );
   comp4 = char_traits<char>::compare ( s4 , s3 , 4 );
   cout << "compare ( s1 , s2 , 2 ) = " << comp1 << endl;
   cout << "compare ( s2 , s3 , 3 ) = " << comp2 << endl;
   cout << "compare ( s3 , s4 , 4 ) = " << comp3 << endl;
   cout << "compare ( s4 , s3 , 4 ) = " << comp4 << endl;
}
```

## <a name="copy"></a>  char_traits::copy

Копирует указанное количество символов из одной строки в другую.

Этот метод является потенциально опасным, так как зависит от вызывающего объекта при проверке правильности переданных значений. Вместо него рекомендуется использовать [char_traits::_Copy_s](#copy_s).

```cpp
static char_type *copy(char_type* _To,
    const char_type* _From,
    size_t _Num);
```

### <a name="parameters"></a>Параметры

*_To*<br/>
Элемент в начале строки или массива символов, предназначенного для получения скопированной последовательности символов.

*_На основе*<br/>
Элемент в начале исходной строки или массива символов для копирования.

*_Num*<br/>
Число элементов, которые следует скопировать.

### <a name="return-value"></a>Возвращаемое значение

Первый элемент, скопированный в строку или массив символов, предназначенный для получения скопированной последовательности символов.

### <a name="remarks"></a>Примечания

Исходная и целевая последовательности символов не должны перекрываться.

### <a name="example"></a>Пример

```cpp
// char_traits_copy.cpp
// compile with: /EHsc /W3
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   char_traits<char>::char_type s1[] = "abcd-1234-abcd";
   char_traits<char>::char_type s2[] = "ABCD-1234";
   char_traits<char>::char_type* result1;
   cout << "The source string is: " << s1 << endl;
   cout << "The destination string is: " << s2 << endl;
   // Note: char_traits::copy is potentially unsafe, consider
   // using char_traits::_Copy_s instead.
   result1 = char_traits<char>::copy ( s1 , s2 , 4 );  // C4996
   cout << "The result1 = copy ( s1 , s2 , 4 ) is: "
        << result1 << endl;
}
```

```Output
The source string is: abcd-1234-abcd
The destination string is: ABCD-1234
The result1 = copy ( s1 , s2 , 4 ) is: ABCD-1234-abcd
```

## <a name="copy_s"></a>  char_traits::_Copy_s

Копирует указанное количество символов из одной строки в другую.

```cpp
static char_type *_Copy_s(
    char_type* dest,
    size_t dest_size,
    const char_type* _From,
    size_t count);
```

### <a name="parameters"></a>Параметры

*dest*<br/>
Строка или массив символов, который должен получить копируемую последовательность символов.

*dest_size*<br/>
Размер *dest*. Если `char_type` — **char**, то это размер в байтах. Если `char_type` — **wchar_t**, то это размер в словах.

*_На основе*<br/>
Исходная строка или массив символов для копирования.

*count*<br/>
Число элементов, которые следует скопировать.

### <a name="return-value"></a>Возвращаемое значение

Строка или массив символов, который должен получить копируемую последовательность символов.

### <a name="remarks"></a>Примечания

Исходная и целевая последовательности символов не должны перекрываться.

### <a name="example"></a>Пример

```cpp
// char_traits__Copy_s.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
    using namespace std;

    char_traits<char>::char_type s1[] = "abcd-1234-abcd";
    char_traits<char>::char_type s2[] = "ABCD-1234";
    char_traits<char>::char_type* result1;
    cout << "The source string is: " << s1 << endl;
    cout << "The destination string is: " << s2 << endl;
    result1 = char_traits<char>::_Copy_s(s1,
        char_traits<char>::length(s1), s2, 4);
    cout << "The result1 = _Copy_s(s1, "
         << "char_traits<char>::length(s1), s2, 4) is: "
         << result1 << endl;
}
```

```Output
The source string is: abcd-1234-abcd
The destination string is: ABCD-1234
The result1 = _Copy_s(s1, char_traits<char>::length(s1), s2, 4) is: ABCD-1234-abcd
```

## <a name="eof"></a>  char_traits::eof

Возвращает символ конца файла (EOF).

```cpp
static int_type eof();
```

### <a name="return-value"></a>Возвращаемое значение

Символ конца файла (EOF).

### <a name="remarks"></a>Примечания

Значение, представляющее конец файла (EOF или WEOF).

Стандарт C++ гласит, что это значение не должно соответствовать допустимому значению `char_type`. Microsoft C++ компилятор налагает это ограничение для типа **char**, но не для типа **wchar_t**. Это демонстрируется в приведенном ниже примере.

### <a name="example"></a>Пример

```cpp
// char_traits_eof.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main()
{
    using namespace std;

    char_traits<char>::char_type ch1 = 'x';
    char_traits<char>::int_type int1;
    int1 = char_traits<char>::to_int_type(ch1);
    cout << "char_type ch1 is '" << ch1 << "' and corresponds to int_type "
         << int1 << "." << endl << endl;

    char_traits<char>::int_type int2 = char_traits<char>::eof();
    cout << "The eof marker for char_traits<char> is: " << int2 << endl;

    char_traits<wchar_t>::int_type int3 = char_traits<wchar_t>::eof();
    cout << "The eof marker for char_traits<wchar_t> is: " << int3 << endl;
}
```

```Output
char_type ch1 is 'x' and corresponds to int_type 120.

The eof marker for char_traits<char> is: -1
The eof marker for char_traits<wchar_t> is: 65535
```

## <a name="eq"></a>  char_traits::eq

Проверяет два символа `char_type` на равенство.

```cpp
static bool eq(const char_type& _Ch1, const char_type& _Ch2);
```

### <a name="parameters"></a>Параметры

*_Ch1*<br/>
Первый из двух символов для проверки на равенство.

*_Ch2*<br/>
Второй из двух символов для проверки на равенство.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если первый символ эквивалентен второму; в противном случае — значение **false**.

### <a name="example"></a>Пример

```cpp
// char_traits_eq.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   char_traits<char>::char_type ch1 =  'x';
   char_traits<char>::char_type ch2 =  'y';
   char_traits<char>::char_type ch3 =  'x';

   // Testing for equality
   bool b1 = char_traits<char>::eq ( ch1 , ch2 );
   if ( b1 )
      cout << "The character ch1 is equal "
           << "to the character ch2." << endl;
   else
      cout << "The character ch1 is not equal "
           << "to the character ch2." << endl;

   // An equivalent and alternatively test procedure
   if ( ch1 == ch3 )
      cout << "The character ch1 is equal "
           << "to the character ch3." << endl;
   else
      cout << "The character ch1 is not equal "
           << "to the character ch3." << endl;
}
```

```Output
The character ch1 is not equal to the character ch2.
The character ch1 is equal to the character ch3.
```

## <a name="eq_int_type"></a>  char_traits::eq_int_type

Проверяет, равны ли два символа, представленные как `int_type`.

```cpp
static bool eq_int_type(const int_type& _Ch1, const int_type& _Ch2);
```

### <a name="parameters"></a>Параметры

*_Ch1*<br/>
Первый из двух символов для проверки на равенство как `int_type`s.

*_Ch2*<br/>
Второй из двух символов для проверки на равенство, представленных как `int_type`.

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если первый символ эквивалентен второму; в противном случае — значение **false**.

### <a name="example"></a>Пример

```cpp
// char_traits_eq_int_type.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   char_traits<char>::char_type ch1 =  'x';
   char_traits<char>::char_type ch2 =  'y';
   char_traits<char>::char_type ch3 =  'x';

   // Converting from char_type to int_type
   char_traits<char>::int_type int1, int2 , int3;
   int1 =char_traits<char>:: to_int_type ( ch1 );
   int2 =char_traits<char>:: to_int_type ( ch2 );
   int3 =char_traits<char>:: to_int_type ( ch3 );

   cout << "The char_types and corresponding int_types are:"
        << "\n    ch1 = " << ch1 << " corresponding to int1 = "
        << int1 << "."
        << "\n    ch2 = " << ch2 << " corresponding to int1 = "
        << int2 << "."
        << "\n    ch3 = " << ch3 << " corresponding to int1 = "
        << int3 << "." << endl << endl;

   // Testing for equality of int_type representations
   bool b1 = char_traits<char>::eq_int_type ( int1 , int2 );
   if ( b1 )
      cout << "The int_type representation of character ch1\n "
           << "is equal to the int_type representation of ch2."
           << endl;
   else
      cout << "The int_type representation of character ch1\n is "
           << "not equal to the int_type representation of ch2."
           << endl;

   // An equivalent and alternatively test procedure
   if ( int1 == int3 )
      cout << "The int_type representation of character ch1\n "
           << "is equal to the int_type representation of ch3."
           << endl;
   else
      cout << "The int_type representation of character ch1\n is "
           << "not equal to the int_type representation of ch3."
           << endl;
}
```

```Output
The char_types and corresponding int_types are:
    ch1 = x corresponding to int1 = 120.
    ch2 = y corresponding to int1 = 121.
    ch3 = x corresponding to int1 = 120.

The int_type representation of character ch1
is not equal to the int_type representation of ch2.
The int_type representation of character ch1
is equal to the int_type representation of ch3.
```

## <a name="find"></a>  char_traits::find

Выполняет поиск первого вхождения указанного символа в диапазоне символов.

```cpp
static const char_type* find(const char_type* str,
    size_t _Num,
    const char_type& _Ch);
```

### <a name="parameters"></a>Параметры

*str*<br/>
Первый искомый символ в строке.

*_Num*<br/>
Число позиций, отсчитываемых от первой, в диапазоне для поиска.

*_Ch*<br/>
Символ для поиска в диапазоне.

### <a name="return-value"></a>Возвращаемое значение

Указатель на первое вхождение указанного символа в диапазоне, если соответствие найдено, в противном случае — пустой указатель.

### <a name="example"></a>Пример

```cpp
// char_traits_find.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   const char* s1 = "f2d-1234-abcd";
   const char* result1;
   cout << "The string to be searched is: " << s1 << endl;

   // Searching for a 'd' in the first 6 positions of string s1
   result1 = char_traits<char>::find ( s1 , 6 , 'd');
   cout << "The character searched for in s1 is: "
        << *result1 << endl;
   cout << "The string beginning with the first occurrence\n "
        << "of the character 'd' is: " << result1 << endl;

   // When no match is found the NULL value is returned
   const char* result2;
   result2 = char_traits<char>::find ( s1 , 3 , 'a');
   if ( result2 == NULL )
      cout << "The result2 of the search is NULL." << endl;
   else
      cout << "The result2 of the search  is: " << result1
           << endl;
}
```

```Output
The string to be searched is: f2d-1234-abcd
The character searched for in s1 is: d
The string beginning with the first occurrence
of the character 'd' is: d-1234-abcd
The result2 of the search is NULL.
```

## <a name="int_type"></a>  char_traits::int_type

Целочисленный тип, который может представлять символ типа `char_type` или символ конца файла (EOF).

```cpp
typedef long int_type;
```

### <a name="remarks"></a>Примечания

Оно должно быть возможно приведение значения типа типов `CharType` для `int_type` а затем обратно в `CharType` без изменения исходного значения.

### <a name="example"></a>Пример

Пример объявления и использования `int_type`[eq_int_type](#eq_int_type).

## <a name="length"></a>  char_traits::length

Возвращает длину строки.

```cpp
static size_t length(const char_type* str);
```

### <a name="parameters"></a>Параметры

*str*<br/>
C-строка, длину которой нужно измерить.

### <a name="return-value"></a>Возвращаемое значение

Количество элементов в измеряемой последовательности, не включая завершающий пустой символ.

### <a name="example"></a>Пример

```cpp
// char_traits_length.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   const char* str1= "Hello";
   cout << "The C-string str1 is: " << str1 << endl;

   size_t lenStr1;
   lenStr1 = char_traits<char>::length ( str1 );
   cout << "The length of C-string str1 is: "
        << lenStr1 << "." << endl;
}
```

```Output
The C-string str1 is: Hello
The length of C-string str1 is: 5.
```

## <a name="lt"></a>  char_traits::lt

Проверяет, меньше ли один символ другого.

```cpp
static bool lt(const char_type& _Ch1, const char_type& _Ch2);
```

### <a name="parameters"></a>Параметры

*_Ch1*<br/>
Первый из двух символов для проверки на "меньше, чем".

*_Ch2*<br/>
Второй из двух символов для проверки на "меньше, чем".

### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если первый символ меньше второго; в противном случае — значение **false**.

### <a name="example"></a>Пример

```cpp
// char_traits_lt.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   char_traits<char>::char_type ch1 =  'x';
   char_traits<char>::char_type ch2 =  'y';
   char_traits<char>::char_type ch3 =  'z';

   // Testing for less than
   bool b1 = char_traits<char>::lt ( ch1 , ch2 );
   if ( b1 )
      cout << "The character ch1 is less than "
           << "the character ch2." << endl;
   else
      cout << "The character ch1 is not less "
           << "than the character ch2." << endl;

   // An equivalent and alternatively test procedure
   if ( ch3 <  ch2 )
      cout << "The character ch3 is less than "
           << "the character ch2." << endl;
   else
      cout << "The character ch3 is not less "
           << "than the character ch2." << endl;
}
```

```Output
The character ch1 is less than the character ch2.
The character ch3 is not less than the character ch2.
```

## <a name="move"></a>  char_traits::move

Копирует указанное количество символов из одной последовательности в другую, возможно перекрывающуюся последовательность.

Этот метод является потенциально опасным, так как зависит от вызывающего объекта при проверке правильности переданных значений. Вместо него рекомендуется использовать [char_traits::_Move_s](#move_s).

```cpp
static char_type *move(char_type* _To,
    const char_type* _From,
    size_t _Num);
```

### <a name="parameters"></a>Параметры

*_To*<br/>
Элемент в начале строки или массива символов, предназначенного для получения скопированной последовательности символов.

*_На основе*<br/>
Элемент в начале исходной строки или массива символов для копирования.

*_Num*<br/>
Количество элементов для копирования из исходной строки.

### <a name="return-value"></a>Возвращаемое значение

Первый элемент *_В* копируется в строку или массив символов, предназначенный для получения скопированной последовательности символов.

### <a name="remarks"></a>Примечания

Исходный и целевой массивы или строки могут перекрываться.

### <a name="example"></a>Пример

```cpp
// char_traits_move.cpp
// compile with: /EHsc /W3
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   char_traits<char>::char_type sFrom1[] =  "abcd-1234-abcd";
   char_traits<char>::char_type sTo1[] =  "ABCD-1234";
   char_traits<char>::char_type* result1;
   cout << "The source string sFrom1 is: " << sFrom1 << endl;
   cout << "The destination stringsTo1 is: " << sTo1 << endl;
   // Note: char_traits::move is potentially unsafe, consider
   // using char_traits::_Move_s instead.
   result1 = char_traits<char>::move ( sTo1 ,  sFrom1 , 4 );  // C4996
   cout << "The result1 = move ( sTo1 , sFrom1 , 4 ) is: "
        << result1 << endl << endl;

   // When source and destination overlap
   char_traits<char>::char_type sToFrom2[] = "abcd-1234-ABCD";
   char_traits<char>::char_type* result2;
   cout << "The source/destination string sToFrom2 is: "
        << sToFrom2 << endl;
   const char* findc = char_traits<char>::find ( sToFrom2 , 4 , 'c' );
   // Note: char_traits::move is potentially unsafe, consider
   // using char_traits::_Move_s instead.
   result2 = char_traits<char>::move ( sToFrom2 , findc , 8 );  // C4996
   cout << "The result2 = move ( sToFrom2 , findc , 8 ) is: "
        << result2 << endl;
}
```

```Output
The source string sFrom1 is: abcd-1234-abcd
The destination stringsTo1 is: ABCD-1234
The result1 = move ( sTo1 , sFrom1 , 4 ) is: abcd-1234

The source/destination string sToFrom2 is: abcd-1234-ABCD
The result2 = move ( sToFrom2 , findc , 8 ) is: cd-1234-4-ABCD
```

## <a name="move_s"></a>  char_traits::_Move_s

Копирует указанное количество символов из одной последовательности в другую, возможно перекрывающуюся последовательность.

```cpp
static char_type *_Move_s(
    char_type* dest,
    size_t dest_size,
    const char_type* _From,
    size_t count);
```

### <a name="parameters"></a>Параметры

*dest*<br/>
Элемент в начале строки или массива символов, предназначенного для получения скопированной последовательности символов.

*dest_size*<br/>
Размер *dest*. Если `char_type` — **char**, то это размер в байтах. Если `char_type` — **wchar_t**, то это размер в словах.

*_На основе*<br/>
Элемент в начале исходной строки или массива символов для копирования.

*count*<br/>
Количество элементов для копирования из исходной строки.

### <a name="return-value"></a>Возвращаемое значение

Первый элемент *dest* копируется в строку или массив символов, предназначенный для получения скопированной последовательности символов.

### <a name="remarks"></a>Примечания

Исходный и целевой массивы или строки могут перекрываться.

### <a name="example"></a>Пример

```cpp
// char_traits__Move_s.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
    using namespace std;

    char_traits<char>::char_type sFrom1[] =  "abcd-1234-abcd";
    char_traits<char>::char_type sTo1[] =  "ABCD-1234";
    char_traits<char>::char_type* result1;
    cout << "The source string sFrom1 is: " << sFrom1 << endl;
    cout << "The destination stringsTo1 is: " << sTo1 << endl;
    result1 = char_traits<char>::_Move_s(sTo1,
        char_traits<char>::length(sTo1), sFrom1, 4);
    cout << "The result1 = _Move_s(sTo1, "
         << "char_traits<char>::length(sTo1), sFrom1, 4) is: "
         << result1 << endl << endl;

    // When source and destination overlap
    char_traits<char>::char_type sToFrom2[] = "abcd-1234-ABCD";
    char_traits<char>::char_type* result2;
    cout << "The source/destination string sToFrom2 is: "
         << sToFrom2 << endl;
    const char* findc = char_traits<char>::find(sToFrom2, 4, 'c');
    result2 = char_traits<char>::_Move_s(sToFrom2,
        char_traits<char>::length(sToFrom2), findc, 8);
    cout << "The result2 = _Move_s(sToFrom2, "
        << "char_traits<char>::length(sToFrom2), findc, 8) is: "
         << result2 << endl;
}
```

```Output
The source string sFrom1 is: abcd-1234-abcd
The destination stringsTo1 is: ABCD-1234
The result1 = _Move_s(sTo1, char_traits<char>::length(sTo1), sFrom1, 4) is: abcd-1234

The source/destination string sToFrom2 is: abcd-1234-ABCD
The result2 = _Move_s(sToFrom2, char_traits<char>::length(sToFrom2), findc, 8) is: cd-1234-4-ABCD
```

## <a name="not_eof"></a>  char_traits::not_eof

Проверяет, не является ли символ символом конца файла (EOF).

```cpp
static int_type not_eof(const int_type& _Ch);
```

### <a name="parameters"></a>Параметры

*_Ch*<br/>
Символ, представленный как `int_type`, для проверки, не является ли он символом конца файла.

### <a name="return-value"></a>Возвращаемое значение

`int_type` Протестирован, представление символа, если `int_type` символа не равно значению символа конца файла.

Если значение `int_type` символа равно значению `int_type` символа конца файла, то возвращается значение **false**.

### <a name="example"></a>Пример

```cpp
// char_traits_not_eof.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( ) {
   using namespace std;

   char_traits<char>::char_type ch1 =  'x';
   char_traits<char>::int_type int1;
   int1 = char_traits<char>:: to_int_type ( ch1 );
   cout << "The char_type ch1 is " << ch1
        << " corresponding to int_type: "
        << int1 << "." << endl;

   // EOF member function
   char_traits <char>::int_type int2 = char_traits<char>::eof ( );
   cout << "The eofReturn is: " << int2 << endl;

   // Testing for EOF or another character
   char_traits <char>::int_type eofTest1, eofTest2;
   eofTest1 = char_traits<char>::not_eof ( int1 );
   if ( !eofTest1 )
      cout << "The eofTest1 indicates ch1 is an EOF character."
              << endl;
   else
      cout << "The eofTest1 returns: " << eofTest1
           << ", which is the character: "
           <<  char_traits<char>::to_char_type ( eofTest1 )
           << "." << endl;

   eofTest2 = char_traits<char>::not_eof ( int2 );
   if ( !eofTest2 )
      cout << "The eofTest2 indicates int2 is an EOF character."
           << endl;
   else
      cout << "The eofTest1 returns: " << eofTest2
           << ", which is the character: "
           <<  char_traits<char>::to_char_type ( eofTest2 )
           << "." << endl;
}
```

```Output
The char_type ch1 is x corresponding to int_type: 120.
The eofReturn is: -1
The eofTest1 returns: 120, which is the character: x.
The eofTest2 indicates int2 is an EOF character.
```

## <a name="off_type"></a>  char_traits::off_type

Целочисленный тип, который может представлять смещения между позициями в потоке.

```cpp
typedef streamoff off_type;
```

### <a name="remarks"></a>Примечания

Этот тип представляет собой целое число со знаком, описывающее объект, который может хранить смещение в байтах, участвующее в различных операциях размещения потока. Обычно является синонимом для [streamoff](../standard-library/ios-typedefs.md#streamoff), но в основном имеет те же свойства, что и данный тип.

## <a name="pos_type"></a>  char_traits::pos_type

Целочисленный тип, который может представлять позиции в потоке.

```cpp
typedef streampos pos_type;
```

### <a name="remarks"></a>Примечания

Этот тип описывает объект, который может хранить все сведения, необходимые для восстановления произвольного указателя позиции файла в потоке. Обычно это синоним [streampos](../standard-library/ios-typedefs.md#streampos), но в любом случае он имеет практически те же свойства, что и этот тип.

## <a name="state_type"></a>  char_traits::state_type

Тип, который представляет состояние преобразования для многобайтовых символов в потоке.

```cpp
typedef implementation-defined state_type;
```

### <a name="remarks"></a>Примечания

Тип описывает объект, который может представлять состояние преобразования. Обычно это синоним для `mbstate_t`, но в любом случае он имеет практически те же свойства, что и этот тип.

## <a name="to_char_type"></a>  char_traits::to_char_type

Преобразует символ `int_type` в соответствующий символ `char_type` и возвращает результат.

```cpp
static char_type to_char_type(const int_type& _Ch);
```

### <a name="parameters"></a>Параметры

*_Ch*<br/>
Символ `int_type`, который должен быть представлен как `char_type`.

### <a name="return-value"></a>Возвращаемое значение

Символ `char_type`, соответствующий символу `int_type`.

Значение *_Ch* , не может быть представлено таким образом, дает неопределенный результат.

### <a name="remarks"></a>Примечания

Операции преобразования [to_int_type](#to_int_type) и `to_char_type` являются обратными по отношению друг к другу, поэтому:

`to_int_type` (`to_char_type` (*x*)) == *x*

для любого `int_type` *x* и

`to_char_type` (`to_int_type` (*x*)) == *x*

для любого `char_type` *x*.

### <a name="example"></a>Пример

```cpp
// char_traits_to_char_type.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;

   char_traits<char>::char_type ch1 =  'a';
   char_traits<char>::char_type ch2 =  'b';
   char_traits<char>::char_type ch3 =  'a';

   // Converting from char_type to int_type
   char_traits<char>::int_type int1, int2 , int3;
   int1 =char_traits<char>:: to_int_type ( ch1 );
   int2 =char_traits<char>:: to_int_type ( ch2 );
   int3 =char_traits<char>:: to_int_type ( ch3 );

   cout << "The char_types and corresponding int_types are:"
        << "\n    ch1 = " << ch1 << " corresponding to int1 = "
        << int1 << "."
        << "\n    ch2 = " << ch2 << " corresponding to int1 = "
        << int2 << "."
        << "\n    ch3 = " << ch3 << " corresponding to int1 = "
        << int3 << "." << endl << endl;

   // Converting from int_type back to char_type
   char_traits<char>::char_type rec_ch1;
   rec_ch1 = char_traits<char>:: to_char_type ( int1);
   char_traits<char>::char_type rec_ch2;
   rec_ch2 = char_traits<char>:: to_char_type ( int2);

   cout << "The recovered char_types and corresponding int_types are:"
        << "\n    recovered ch1 = " << rec_ch1 << " from int1 = "
        << int1 << "."
        << "\n    recovered ch2 = " << rec_ch2 << " from int2 = "
        << int2 << "." << endl << endl;

   // Testing that the conversions are inverse operations
   bool b1 = char_traits<char>::eq ( rec_ch1 , ch1 );
   if ( b1 )
      cout << "The recovered char_type of ch1"
           << " is equal to the original ch1." << endl;
   else
      cout << "The recovered char_type of ch1"
           << " is not equal to the original ch1." << endl;

   // An equivalent and alternatively test procedure
   if ( rec_ch2 == ch2 )
      cout << "The recovered char_type of ch2"
           << " is equal to the original ch2." << endl;
   else
      cout << "The recovered char_type of ch2"
           << " is not equal to the original ch2." << endl;
}
```

```Output
The char_types and corresponding int_types are:
    ch1 = a corresponding to int1 = 97.
    ch2 = b corresponding to int1 = 98.
    ch3 = a corresponding to int1 = 97.

The recovered char_types and corresponding int_types are:
    recovered ch1 = a from int1 = 97.
    recovered ch2 = b from int2 = 98.

The recovered char_type of ch1 is equal to the original ch1.
The recovered char_type of ch2 is equal to the original ch2.
```

## <a name="to_int_type"></a>  char_traits::to_int_type

Преобразует символ `char_type` в соответствующий символ `int_type` и возвращает результат.

```cpp
static int_type to_int_type(const char_type& _Ch);
```

### <a name="parameters"></a>Параметры

*_Ch*<br/>
Символ `char_type`, который должен быть представлен как `int_type`.

### <a name="return-value"></a>Возвращаемое значение

Символ `int_type`, соответствующий символу `char_type`.

### <a name="remarks"></a>Примечания

Операции преобразования `to_int_type` и [to_char_type](#to_char_type) являются обратными по отношению друг к другу, поэтому:

`to_int_type` (`to_char_type` (*x*)) == *x*

для любого `int_type` *x*, и

`to_char_type` (`to_int_type` (*x*)) == *x*

для любого `char_type` *x*.

### <a name="example"></a>Пример

```cpp
// char_traits_to_int_type.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

int main( )
{
   using namespace std;
   char_traits<char>::char_type ch1 = 'a';
   char_traits<char>::char_type ch2 = 'b';
   char_traits<char>::char_type ch3 = 'a';

   // Converting from char_type to int_type
   char_traits<char>::int_type int1, int2 , int3;
   int1 =char_traits<char>:: to_int_type ( ch1 );
   int2 =char_traits<char>:: to_int_type ( ch2 );
   int3 =char_traits<char>:: to_int_type ( ch3 );

   cout << "The char_types and corresponding int_types are:"
        << "\n    ch1 = " << ch1 << " corresponding to int1 = "
        << int1 << "."
        << "\n    ch2 = " << ch2 << " corresponding to int1 = "
        << int2 << "."
        << "\n    ch3 = " << ch3 << " corresponding to int1 = "
        << int3 << "." << endl << endl;

   // Converting from int_type back to char_type
   char_traits<char>::char_type rec_ch1;
   rec_ch1 = char_traits<char>:: to_char_type ( int1);
   char_traits<char>::char_type rec_ch2;
   rec_ch2 = char_traits<char>:: to_char_type ( int2);

   cout << "The recovered char_types and corresponding int_types are:"
        << "\n    recovered ch1 = " << rec_ch1 << " from int1 = "
        << int1 << "."
        << "\n    recovered ch2 = " << rec_ch2 << " from int2 = "
        << int2 << "." << endl << endl;

   // Testing that the conversions are inverse operations
   bool b1 = char_traits<char>::eq ( rec_ch1 , ch1 );
   if ( b1 )
      cout << "The recovered char_type of ch1"
           << " is equal to the original ch1." << endl;
   else
      cout << "The recovered char_type of ch1"
           << " is not equal to the original ch1." << endl;

   // An equivalent and alternatively test procedure
   if ( rec_ch2 == ch2 )
      cout << "The recovered char_type of ch2"
           << " is equal to the original ch2." << endl;
   else
      cout << "The recovered char_type of ch2"
           << " is not equal to the original ch2." << endl;
}
```

```Output
The char_types and corresponding int_types are:
    ch1 = a corresponding to int1 = 97.
    ch2 = b corresponding to int1 = 98.
    ch3 = a corresponding to int1 = 97.

The recovered char_types and corresponding int_types are:
    recovered ch1 = a from int1 = 97.
    recovered ch2 = b from int2 = 98.

The recovered char_type of ch1 is equal to the original ch1.
The recovered char_type of ch2 is equal to the original ch2.
```

## <a name="see-also"></a>См. также

[Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
