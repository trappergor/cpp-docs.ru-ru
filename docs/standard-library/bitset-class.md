---
title: Класс bitset
ms.date: 03/27/2019
f1_keywords:
- bitset/std::bitset
- bitset/std::bitset::element_type
- bitset/std::bitset::all
- bitset/std::bitset::any
- bitset/std::bitset::count
- bitset/std::bitset::flip
- bitset/std::bitset::none
- bitset/std::bitset::reset
- bitset/std::bitset::set
- bitset/std::bitset::size
- bitset/std::bitset::test
- bitset/std::bitset::to_string
- bitset/std::bitset::to_ullong
- bitset/std::bitset::to_ulong
- bitset/std::bitset::reference
helpviewer_keywords:
- std::bitset [C++]
- std::bitset [C++], element_type
- std::bitset [C++], all
- std::bitset [C++], any
- std::bitset [C++], count
- std::bitset [C++], flip
- std::bitset [C++], none
- std::bitset [C++], reset
- std::bitset [C++], set
- std::bitset [C++], size
- std::bitset [C++], test
- std::bitset [C++], to_string
- std::bitset [C++], to_ullong
- std::bitset [C++], to_ulong
- std::bitset [C++], reference
ms.assetid: 28b86964-87b4-429c-8124-b6c251b6c50b
ms.openlocfilehash: 2337a5e8355006ef2c05874b9e3e46b469c41beb
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243345"
---
# <a name="bitset-class"></a>Класс bitset

Описывает тип объекта, который хранит последовательность, состоящую из фиксированного числа битов, предоставляющих компактный способ хранения флагов для набора элементов или условий. Класс bitset поддерживает операции над объектами типа bitset, которые содержат коллекцию битов и обеспечивают доступ в константном времени к каждому биту.

## <a name="syntax"></a>Синтаксис

```cpp
template <size_t N>
class bitset
```

### <a name="parameters"></a>Параметры

*N*\
Указывает количество битов в объекте bitset в виде ненулевого целого типа `size_t` , должно быть известно во время компиляции.

## <a name="remarks"></a>Примечания

В отличие от аналогичного [класса vector\<bool>](../standard-library/vector-bool-class.md) у класса bitset нет итераторов, и он не является контейнером библиотеки стандартных программ C++. Он также отличается от vector\<bool> тем, что его размер зафиксирован во время компиляции в соответствии с размером, указанным в параметре шаблона *N* при объявлении **bitset\<N\>** .

Бит задан, если его значение равно 1, и сброшен, если его значение равно 0. Перевернуть или инвертировать бит — значит изменить его значение с 1 на 0 или с 0 на 1. *N* битов в bitset индексируются по целым значениям от 0 до *N* – 1, где 0 — это индекс первой позиции бита, а *N* – 1 — индекс конечной позиции бита.

## <a name="members"></a>Участники

### <a name="constructors"></a>Конструкторы

|||
|-|-|
|[bitset](#bitset)|Создает объект класса `bitset\<N>` и инициализирует биты с нулевым значением до определенного указанного значения или до значений, полученных из символов в строке.|

### <a name="typedefs"></a>Typedefs

|||
|-|-|
|[element_type](#element_type)|Тип, которое является синонимом для типа данных **bool** и может использоваться для ссылки на биты элементов в `bitset`.|

### <a name="functions"></a>Функции

|||
|-|-|
|[all](#all)|Проверяет все биты в этом `bitset` для определения того, имеют ли они все значение **true**.|
|[any](#any)|Функция-член проверяет, равен ли какой-либо бит в последовательности 1.|
|[count](#count)|Эта функция-член возвращает количество бит, заданных в последовательности бит.|
|[flip](#flip)|Инвертирует все биты в `bitset` или инвертирует один бит в указанной позиции.|
|[none](#none)|Проверяет, присвоено ли хотя бы одному биту в объекте `bitset` значение 1.|
|[reset](#reset)|Сбрасывает все биты в `bitset` в значение 0 или сбрасывает бит в указанной позиции в 0.|
|[set](#set)|Присваивает всем битам в `bitset` значение 1 или присваивает биту в указанной позиции значение 1.|
|[size](#size)|Возвращает количество бит в объекте `bitset`.|
|[test](#test)|Проверяет, присвоено ли биту в указанной позиции в `bitset` значение 1.|
|[to_string](#to_string)|Преобразует объект `bitset` в строковое представление.|
|[to_ullong](#to_ullong)|Возвращает сумму битовых значений в `bitset` как **long long без знака**.|
|[to_ulong](#to_ulong)|Преобразует `bitset` объект **unsigned long** , чтобы получить последовательность его битов, если используется для инициализации `bitset`.|

### <a name="classes"></a>Классы

|||
|-|-|
|[reference](#reference)|Прокси-класс, который предоставляет ссылки на биты в объекте `bitset`, используемые для доступа к отдельным битам и их обработки в качестве вспомогательного класса для `operator[]` класса `bitset`.|

### <a name="operators"></a>Операторы

|||
|-|-|
|[operator!=](#op_neq)|Проверяет целевой объект `bitset` на неравенство относительно указанного объекта `bitset`.|
|[оператор&=](#op_and_eq)|Выполняет побитовое сочетание битовых массивов с использованием логической операции `AND`.|
|[оператор<<](#op_lshift)|Сдвигает биты в `bitset` влево на указанное число позиций и возвращает результат в новом объекте `bitset`.|
|[оператор<<=](#op_lshift_eq)|Сдвигает биты в `bitset` влево на указанное число позиций и возвращает результат в целевом объекте `bitset`.|
|[operator==](#op_eq_eq)|Проверяет целевой объект `bitset` на равенство относительно указанного объекта `bitset`.|
|[оператор>>](#op_rshift)|Сдвигает биты в `bitset` вправо на указанное число позиций и возвращает результат в новом объекте `bitset`.|
|[оператор>>=](#op_rshift_eq)|Сдвигает биты в `bitset` вправо на указанное число позиций и возвращает результат в целевом объекте `bitset`.|
|[оператор&#91;&#93;](#op_at)|Возвращает ссылку на бит в указанной позиции в `bitset`, если `bitset` может быть изменен; в противном случае возвращается значение бита в этой позиции.|
|[оператор^=](#op_xor_eq)|Выполняет побитовое сочетание битовых массивов с использованием эксклюзивной операции `OR`.|
|[оператор&#124;=](#op_or_eq)|Выполняет побитовое сочетание битовых массивов с использованием инклюзивной операции `OR`.|
|[оператор~](#op_not)|Инвертирует все биты в целевом объекте `bitset` и возвращает результат.|

### <a name="structures"></a>Структуры

|||
|-|-|
|[hash](#hash)||

### <a name="all"></a> Все

Проверяет все биты в этом битовом массиве, чтобы определить, имеют ли они все значение true.

```cpp
bool all() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Возвращает значение true, если все биты в этом массиве имеют значение true. Возвращает **false**, если хотя бы один бит имеет значение false.

### <a name="any"></a> Любой

Проверяет, равен ли какой-либо бит в последовательности 1.

```cpp
bool any() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если хотя бы один бит в битовом массиве равен 1; значение **false**, если все биты равны 0.

#### <a name="example"></a>Пример

```cpp
// bitset_any.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 6 );
   bool b, rb;

   cout << "The original bitset b1( 6 ) is: ( "<< b1 << " )"
        << endl;

   b = b1.any ( );

   if ( b )
      cout << "At least one of the bits in bitset is set to 1."
           << endl;
   else
      cout << "None of the bits in bitset are set to 1."
           << endl;

   bitset<5> rb1;
   rb1 = b1.reset ( );

   cout << "The reset bitset is: ( "<< b1 << " )"
        << endl;

   rb = rb1.any ( );

   if ( rb )
      cout << "At least one of the bits in the reset bitset "
           << "are set to 1." << endl;
   else
      cout << "None of the bits in bitset b1 are set to 1."
           << endl;
}
```

```Output
The original bitset b1( 6 ) is: ( 00110 )
At least one of the bits in bitset is set to 1.
The reset bitset is: ( 00000 )
None of the bits in bitset b1 are set to 1.
```

### <a name="bitset"></a> битовый массив

Создает объект класса `bitset\<N>` и инициализирует биты с нулевым значением, с определенным указанным значением или со значениями, полученными из символов в строке.

```cpp
bitset();

bitset(
    unsigned long long val);

explicit bitset(
    const char* _CStr);

template <class CharType,
    class Traits,
    class Allocator>
explicit bitset(
    const basic_string<CharType, Traits, Allocator>& str,
    typename basic_string<CharType, Traits, Allocator>::size_type _Pos = 0);

template <class CharType,
    class Traits,
    class Allocator>
explicit bitset(
    const basic_string<CharType, Traits, Allocator>& str,
    typename basic_string<CharType, Traits, Allocator>::size_type _Pos,
    typename basic_string<CharType, Traits, Allocator>::size_type count,
    CharType _Zero = CharType ('0'),
    CharType _One = CharType ('1'));
```

#### <a name="parameters"></a>Параметры

*Val*\
Целое число без знака, чье представление с основанием 2 используется для инициализации битов в конструируемом битовом массиве.

*STR*\
Строка из нулей и единиц используется для инициализации значений битов в битовом массиве.

*_CStr*\
Строка C-стиля из нулей и единиц используется для инициализации значений битов в битовом массиве.

*_Pos*\
Позиция символа в строке, если считать слева направо начиная с нуля, используемая для инициализации первого бита в битовом массиве.

*число*\
Число символов в строке, которая используется для предоставления начальных значений битам в битовом массиве.

*_Zero*\
Символ, который используется для представления нуля. Значение по умолчанию — 0.

*_Одно*\
Символ, который используется для представления единицы. Значение по умолчанию — 1.

#### <a name="remarks"></a>Примечания

Для создания объектов класса `bitset\<N>` можно использовать три конструктора.

- Первый конструктор не принимает параметры, создает объект класса `bitset\<N>` и инициализирует все N битов значением по умолчанию 0.

- Второй конструктор создает объект класса `bitset\<N>` и инициализирует биты с помощью одного **long long без знака** параметра.

- Третий конструктор создает объект класса `bitset\<N>`, инициализируя N битов значениями, соответствующими символам, которые предоставляются в символьной строке C-стиля, состоящей из нулей и единиц. Конструктор вызывается без приведения строки в тип string: `bitset<5> b5("01011");`

Кроме того, существует также два шаблона конструктора.

- Первый шаблон конструктора создает объект класса `bitset\<N>` и инициализирует биты из символов, предоставленных в строке из нулей и единиц. Если в строке обнаруживаются символы, отличные от 0 или 1, конструктор создает объект класса [invalid argument](../standard-library/invalid-argument-class.md). Если указанное положение ( *_Pos*) выходит за пределы длины строки, то конструктор создает объект класса [out_of_range](../standard-library/out-of-range-class.md). Конструктор задает только те биты в позиции *j* в битовом массиве, для которых символ в строке в позиции `_Pos + j` равен 1. По умолчанию *_Pos* равно 0.

- Второй шаблон конструктора похож на первый, но содержит дополнительный параметр (*число*), используемый для указания числа битов для инициализации. Он также включает два необязательных параметра, *_Zero* и *_одно*, которые указывают, какой символ в *str* должен интерпретироваться как бит 0 и 1 бит, соответственно.

#### <a name="example"></a>Пример

```cpp
// bitset_bitset.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   // Using the default constructor
   using namespace std;
   bitset<2> b0;
   cout << "The set of bits in bitset<2> b0 is: ( "
        << b0 << " )." << endl;

   // Using the second member function
   bitset<5> b1 ( 6 );
   cout << "The set of bits in bitset<5> b1( 6 ) is: ( "
        << b1 << " )." << endl;

   // The template parameter N can be an expresssion
   bitset< 2 * sizeof ( int ) > b2;
   cout << "The set of bits in bitset<2 * sizeof ( int ) > b2 is: ( "
        << b2 << " )." << endl;

   // The base two representation will be truncated
   // if its length exceeds the size of the bitset
   bitset<3> b3 ( 6 );
   cout << "The set of bits in bitset<3> b3( 6 ) is ( "
        << b3 << " )." << endl;

   // Using a c-style string to initialize the bitset
    bitset<7> b3andahalf ( "1001001" );
    cout << "The set of bits in bitset<7> b3andahalf ( \"1001001\" )"
         << " is ( " << b3andahalf << " )." << endl;

   // Using the fifth member function with the first parameter
   string bitval4 ( "10011" );
   bitset<5> b4 ( bitval4 );
   cout << "The set of bits in bitset<5> b4( bitval4 ) is ( "
        << b4 << " )." << endl;

   // Only part of the string may be used for initialization

   // Starting at position 3 for a length of 6 (100110)
   string bitval5 ("11110011011");
   bitset<6> b5 ( bitval5, 3, 6 );
   cout << "The set of bits in bitset<11> b5( bitval, 3, 6 ) is ( "
        << b5 << " )." << endl;

   // The bits not initialized with part of the string
   // will default to zero
   bitset<11> b6 ( bitval5, 3, 5 );
   cout << "The set of bits in bitset<11> b6( bitval5, 3, 5 ) is ( "
        << b6 << " )." << endl;

   // Starting at position 2 and continue to the end of the string
   bitset<9> b7 ( bitval5, 2 );
   cout << "The set of bits in bitset<9> b7( bitval, 2 ) is ( "
        << b7 << " )." << endl;
}
```

```Output
The set of bits in bitset<2> b0 is: ( 00 ).
The set of bits in bitset<5> b1( 6 ) is: ( 00110 ).
The set of bits in bitset<2 * sizeof ( int ) > b2 is: ( 00000000 ).
The set of bits in bitset<3> b3( 6 ) is ( 110 ).
The set of bits in bitset<5> b4( bitval4 ) is ( 10011 ).
The set of bits in bitset<11> b5( bitval, 3, 6 ) is ( 100110 ).
The set of bits in bitset<11> b6( bitval5, 3, 5 ) is ( 00000010011 ).
The set of bits in bitset<9> b7( bitval, 2 ) is ( 110011011 ).
```

### <a name="count"></a> число

Возвращает количество бит, заданных в последовательности бит.

```cpp
size_t count() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Количество бит, заданных в последовательности бит.

#### <a name="example"></a>Пример

```cpp
// bitset_count.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
    using namespace std;

    bitset<5> b1(4);

    cout << "The collection of bits in the original bitset is: ( "
         << b1 << " )" << endl;

    size_t i;
    i = b1.count();
    cout << "The number of bits in the bitset set to 1 is: "
         << i << "." << endl;

    bitset<5> fb1;
    fb1 = b1.flip();

    cout << "The collection of flipped bits in the modified bitset "
         << "is: ( " << b1 << " )" << endl;

    size_t ii;
    ii = fb1.count();
    cout << "The number of bits in the bitset set to 1 is: "
         << ii << "." << endl;
}
```

```Output
The collection of bits in the original bitset is: ( 00100 )
The number of bits in the bitset set to 1 is: 1.
The collection of flipped bits in the modified bitset is: ( 11011 )
The number of bits in the bitset set to 1 is: 4.
```

### <a name="element_type"></a> element_type

Тип, которое является синонимом для типа данных **bool** и может использоваться для ссылки на биты элементов в битовом массиве.

```cpp
typedef bool element_type;
```

#### <a name="example"></a>Пример

```cpp
// bitset_elem_type.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;

   bitset<3> b1 ( 2 );
   cout << "Original bitset b1(6) is: ( "<< b1 << " )"
        << endl;

   //Compare two ways to reference bits in a bitset
   bool b;
   bitset<5>::element_type e;

   b = b1.test ( 2 );
   if ( b )
      cout << "The bit at position 2 of bitset b1"
           << "has a value of 1." << endl;
   else
      cout << "The bit at position 2 of bitset b1"
           << "has a value of 0." << endl;
   b1[2] = 1;
   cout << "Bitset b1 modified by b1[2] = 1 is: ( "<< b1 << " )"
        << endl;

   e = b1.test ( 2 );
   if ( e )
      cout << "The bit at position 2 of bitset b1"
           << "has a value of 1." << endl;
   else
      cout << "The bit at position 2 of bitset b1"
           << "has a value of 0." << endl;
}
```

```Output
Original bitset b1(6) is: ( 010 )
The bit at position 2 of bitset b1has a value of 0.
Bitset b1 modified by b1[2] = 1 is: ( 110 )
The bit at position 2 of bitset b1has a value of 1.
```

### <a name="flip"></a> перевернуть

Инвертирует значения всех битов в битовом массиве или инвертирует один бит в указанной позиции.

```cpp
bitset\<N>& flip();
bitset\<N>& flip(size_t _Pos);
```

#### <a name="parameters"></a>Параметры

*_Pos*\
Позиция бита, значение которого следует инвертировать.

#### <a name="return-value"></a>Возвращаемое значение

Копия измененного битового массива, для которого была вызвана функция-член.

#### <a name="remarks"></a>Примечания

Вторая функция-член вызывает [out_of_range](../standard-library/out-of-range-class.md) исключение, если положение, указанное в качестве параметра — больше, чем размер *N* из **bitset\<**  *N* **>** биты которого были инвертированы.

#### <a name="example"></a>Пример

```cpp
// bitset_flip.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;
   bitset<5> b1 ( 6 );

   cout << "The collection of bits in the original bitset is: ( "
        << b1 << " )" << endl;

   bitset<5> fb1;
   fb1 = b1.flip ( );

   cout << "After flipping all the bits, the bitset becomes: ( "
        << fb1 << " )" << endl;

   bitset<5> f3b1;
   f3b1 = b1.flip ( 3 );

   cout << "After flipping the fourth bit, the bitset becomes: ( "
        << f3b1 << " )" << endl << endl;

   bitset<5> b2;
   int i;
   for ( i = 0 ; i <= 4 ; i++ )
   {
      b2.flip(i);
      cout << b2 << "  The bit flipped is in position "
           << i << ".\n";
   }
}
```

```Output
The collection of bits in the original bitset is: ( 00110 )
After flipping all the bits, the bitset becomes: ( 11001 )
After flipping the fourth bit, the bitset becomes: ( 10001 )

00001  The bit flipped is in position 0.
00011  The bit flipped is in position 1.
00111  The bit flipped is in position 2.
01111  The bit flipped is in position 3.
11111  The bit flipped is in position 4.
```

### <a name="hash"></a> хэш

```cpp
template <class T> struct hash;
template <size_t N> struct hash<bitset<N>>;
```

### <a name="none"></a> Нет

Проверяет, присвоено ли хотя бы одному биту в объекте bitset значение 1.

```cpp
bool none() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Значение **true,** , если ни одному биту в битовом массиве не присвоено значение 1; значение **false**, если хотя бы один бит равен 1.

#### <a name="example"></a>Пример

```cpp
// bitset_none.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 6 );
   bool b, rb;

   cout << "Original bitset b1(6) is: ( " << b1 << " )"
        << endl;

   b = b1.none ( );

   if ( b )
      cout << "None of the bits in bitset b1 are set to 1."
           << endl;
   else
      cout << "At least one of the bits in bitset b1 is set to 1."
           << endl;

   bitset<5> rb1;
   rb1 = b1.reset ( );
   rb = rb1.none ( );
   if ( rb )
      cout << "None of the bits in bitset b1 are set to 1."
           << endl;
   else
      cout << "At least one of the bits in bitset b1 is set to 1."
           << endl;
}
```

```Output
Original bitset b1(6) is: ( 00110 )
At least one of the bits in bitset b1 is set to 1.
None of the bits in bitset b1 are set to 1.
```

### <a name="op_neq"></a> оператор! =

Проверяет целевой битовый массив на неравенство относительно указанного битового массива.

```cpp
bool operator!=(const bitset\<N>& right) const;
```

#### <a name="parameters"></a>Параметры

*Правильно*\
Битовый массив, который должен сравниваться с целевым битовым массивом на неравенство.

#### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если битовые массивы различаются; значение **false**, если они совпадают.

#### <a name="remarks"></a>Примечания

Битовые массивы должны иметь одинаковый размер для проверки на неравенство функцией оператора-члена.

#### <a name="example"></a>Пример

```cpp
// bitset_op_NE.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 7 );
   bitset<5> b2 ( 7 );
   bitset<5> b3 ( 2 );
   bitset<4> b4 ( 7 );

   if ( b1 != b2 )
      cout << "Bitset b1 is different from bitset b2." << endl;
   else
      cout << "Bitset b1 is the same as bitset b2." << endl;

   if ( b1 != b3 )
      cout << "Bitset b1 is different from bitset b3." << endl;
   else
      cout << "Bitset b1 is the same as bitset b3." << endl;

   // This would cause an error because bitsets must have the
   // same size to be tested
   // if ( b1 != b4 )
   //   cout << "Bitset b1 is different from bitset b4." << endl;
   // else
   //   cout << "Bitset b1 is the same as bitset b4." << endl;
}
```

```Output
Bitset b1 is the same as bitset b2.
Bitset b1 is different from bitset b3.
```

### <a name="op_and_eq"></a> Оператор&amp;=

Выполняет побитовое сочетание битовых массивов с использованием логической операции `AND`.

```cpp
bitset\<N>& operator&=(const bitset\<N>& right);
```

#### <a name="parameters"></a>Параметры

*Правильно*\
Битовый массив для побитового сочетания с целевым битовым массивом.

#### <a name="return-value"></a>Возвращаемое значение

Измененный целевой битовый массив, полученный в результате побитовой `AND` операцию с битовым массивом, указанным в качестве параметра.

#### <a name="remarks"></a>Примечания

Два бита, скомбинированные с `AND` оператор return **true** Если каждый бит имеет значение true; в противном случае их комбинация в дополнительной возвращает **false**.

Битовые массивы должны иметь одинаковый размер для побитового сочетания с `AND` оператор функцией оператора-члена.

#### <a name="example"></a>Пример

```cpp
// bitset_op_bitwise.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 7 );
   bitset<5> b2 ( 11 );
   bitset<4> b3 ( 7 );

   cout << "The target bitset b1 is:    ( "<< b1 << " )." << endl;
   cout << "The parameter bitset b2 is: ( "<< b2 << " )." << endl;
   cout << endl;

   b1 &= b2;
   cout << "After bitwise AND combination,\n"
        << "the target bitset b1 becomes:   ( "<< b1 << " )."
        << endl;

   // Note that the parameter-specified bitset is unchanged
   cout << "The parameter bitset b2 remains: ( "<< b2 << " )."
        << endl;

   // The following would cause an error because the bisets
   // must be of the same size to be combined
   // b1 &= b3;
}
```

```Output
The target bitset b1 is:    ( 00111 ).
The parameter bitset b2 is: ( 01011 ).

After bitwise AND combination,
the target bitset b1 becomes:   ( 00011 ).
The parameter bitset b2 remains: ( 01011 ).
```

### <a name="op_lshift"></a> Оператор\<\<

Сдвигает биты в битовом массиве влево на указанное число позиций и возвращает результат в новый битовый массив.

```cpp
bitset\<N> operator<<(size_t _Pos) const;
```

#### <a name="parameters"></a>Параметры

*_Pos*\
Количество позиций, на которое должны сдвигаться влево биты из битового массива.

#### <a name="return-value"></a>Возвращаемое значение

Измененный битовый массив с битами, сдвинутыми влево на требуемое количество позиций.

#### <a name="remarks"></a>Примечания

Функция оператора-члена возвращает **bitset**( **\*this**) **<<= pos,** где [<<=](#op_lshift_eq) сдвигает биты в битовом массиве влево на указанное число позиций и возвращает результат в целевой битовый массив.

#### <a name="example"></a>Пример

```cpp
// bitset_op_LS.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 7 );

   cout << "The bitset b1 is: ( "<< b1 << " )." << endl;

   bitset<5> b2;
   b2 = b1 << 2;

   cout << "After shifting the bits 2 positions to the left,\n"
        << " the bitset b2 is: ( "<< b2 << " )."
        << endl;

   bitset<5> b3 = b2 >> 1;

   cout << "After shifting the bits 1 position to the right,\n"
        << " the bitset b3 is: ( " << b3 << " )."
        << endl;
}
```

### <a name="op_lshift_eq"></a> Оператор&lt;&lt;=

Сдвигает биты в массиве битов влево на указанное число позиций и возвращает результат в целевой битовый массив.

```cpp
bitset\<N>& operator<<=(size_t _Pos);
```

#### <a name="parameters"></a>Параметры

*_Pos*\
Количество позиций, на которое должны сдвигаться влево биты из битового массива.

#### <a name="return-value"></a>Возвращаемое значение

Целевой битовый массив, измененный так, что биты сдвинуты влево на требуемое количество позиций.

#### <a name="remarks"></a>Примечания

Если отсутствуют элементы для сдвига в эту позицию, функция сбрасывает бит в значение 0.

#### <a name="example"></a>Пример

```cpp
// bitset_op_LSE.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;
   bitset<5> b1 ( 7 );
   cout << "The target bitset b1 is: ( "<< b1 << " )." << endl;
   b1 <<= 2;
   cout << "After shifting the bits 2 positions to the left,\n"
        << "the target bitset b1 becomes: ( "<< b1 << " )."
        << endl;
}
```

```Output
The target bitset b1 is: ( 00111 ).
After shifting the bits 2 positions to the left,
the target bitset b1 becomes: ( 11100 ).
```

### <a name="op_eq_eq"></a> оператор ==

Проверяет целевой битовый массив на равенство относительно указанного битового массива.

```cpp
bool operator==(const bitset\<N>& right) const;
```

#### <a name="parameters"></a>Параметры

*Правильно*\
Битовый массив, который должен сравниваться с целевым битовым массивом на равенство.

#### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если битовые массивы совпадают; значение **false**, если они различаются.

#### <a name="remarks"></a>Примечания

Битовые массивы должны иметь одинаковый размер для проверки на равенство функцией оператора-члена.

#### <a name="example"></a>Пример

```cpp
// bitset_op_EQ.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;
   bitset<5> b1 ( 7 );
   bitset<5> b2 ( 7 );
   bitset<5> b3 ( 2 );
   bitset<4> b4 ( 7 );

   if ( b1 == b2 )
      cout << "Bitset b1 is the same as bitset b2." << endl;
   else
      cout << "Bitset b1 is different from bitset b2." << endl;

   if ( b1 == b3 )
      cout << "Bitset b1 is the same as bitset b3." << endl;
   else
      cout << "Bitset b1 is different from bitset b3." << endl;

   // This would cause an error because bitsets must have the
   // same size to be tested
   // if ( b1 == b4 )
   //   cout << "Bitset b1 is the same as bitset b4." << endl;
   // else
   //   cout << "Bitset b1 is different from bitset b4." << endl;
}
```

```Output
Bitset b1 is the same as bitset b2.
Bitset b1 is different from bitset b3.
```

### <a name="op_rshift"></a> Оператор&gt;&gt;

Сдвигает биты в битовом массиве вправо на указанное число позиций и возвращает результат в новый битовый массив.

```cpp
bitset\<N> operator>>(size_t _Pos) const;
```

#### <a name="parameters"></a>Параметры

*_Pos*\
Количество позиций, на которое должны сдвигаться вправо биты из битового массива.

#### <a name="return-value"></a>Возвращаемое значение

Новый битовый массив, в котором биты сдвинуты вправо на требуемое количество позиций по отношению к целевому массиву битов.

#### <a name="example"></a>Пример

```cpp
// bitset_op_RS.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;
   bitset<5> b1 ( 7 );
   cout << "The bitset b1 is: ( "<< b1 << " )." << endl;

   bitset<5> b2;
   b2 = b1 << 2;

   cout << "After shifting the bits 2 positions to the left,\n"
        << "the bitset b2 is: ( "<< b2 << " )."
        << endl;
   bitset<5> b3 = b2 >> 1;

   cout << "After shifting the bits 1 position to the right,\n"
        << "the bitset b3 is: ( " << b3 << " )."
        << endl;
}
```

```Output
The bitset b1 is: ( 00111 ).
After shifting the bits 2 positions to the left,
the bitset b2 is: ( 11100 ).
After shifting the bits 1 position to the right,
the bitset b3 is: ( 01110 ).
```

### <a name="op_rshift_eq"></a> Оператор&gt;&gt;=

Сдвигает биты в массиве битов вправо на указанное число позиций и возвращает результат в целевой битовый массив.

```cpp
bitset\<N>& operator>>=(size_t _Pos);
```

#### <a name="parameters"></a>Параметры

*_Pos*\
Количество позиций, на которое должны сдвигаться вправо биты из битового массива.

#### <a name="return-value"></a>Возвращаемое значение

Целевой битовый массив, измененный так, что биты сдвинуты вправо на требуемое количество позиций.

#### <a name="remarks"></a>Примечания

Если отсутствуют элементы для сдвига в эту позицию, функция сбрасывает бит в значение 0.

#### <a name="example"></a>Пример

```cpp
// bitset_op_RSE.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;
   bitset<5> b1 ( 28 );
   cout << "The target bitset b1 is: ( "<< b1 << " )." << endl;

   b1 >>= 2;
   cout << "After shifting the bits 2 positions to the right,\n"
        << "the target bitset b1 becomes: ( "<< b1 << " )."
        << endl;
}
```

```Output
The target bitset b1 is: ( 11100 ).
After shifting the bits 2 positions to the right,
the target bitset b1 becomes: ( 00111 ).
```

### <a name="op_at"></a> оператор]

Возвращает ссылку на бит в указанной позиции в битовом массиве, если этот битовый массив может быть изменен; в противном случае возвращается значение бита в этой позиции.

```cpp
bool operator[](size_t _Pos) const;
reference operator[](size_t _Pos);
```

#### <a name="parameters"></a>Параметры

*_Pos*\
Позиция расположения бита в битовом массиве.

#### <a name="remarks"></a>Примечания

Если вы задаете [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md) в качестве 1 или 2 в своей сборке, при попытке доступа к элементу вне границ массива битов в исполняемом файле произойдет ошибка времени выполнения. Дополнительные сведения см. в разделе [Проверенные итераторы](../standard-library/checked-iterators.md).

#### <a name="example"></a>Пример

```cpp
// bitset_op_REF.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;
   bool b;
   bitset<5> b1 ( 6 );
   cout << "The initialized bitset<5> b1( 2 ) is: ( "<< b1 << " )."
        << endl;

   int i;
   for ( i = 0 ; i <= 4 ; i++ )
   {
      b = b1[ i ];
      cout << "  The bit in position "
           << i << " is " << b << ".\n";
   }
}
```

### <a name="op_xor_eq"></a> оператор ^ =

Выполняет побитовое сочетание битовых массивов с использованием эксклюзивной операции `OR`.

```cpp
bitset\<N>& operator^=(const bitset\<N>& right);
```

#### <a name="parameters"></a>Параметры

*Правильно*\
Битовый массив для побитового сочетания с целевым битовым массивом.

#### <a name="return-value"></a>Возвращаемое значение

Измененный целевой битовый массив, полученный в результате побитовой исключающей операции `OR` с битовым массивом, указанным в качестве параметра.

#### <a name="remarks"></a>Примечания

Два бита, скомбинированные с помощью исключающего оператора **OR**, возвращают значение **true**, если один бит (но не оба бита) оценивается как **true**; в противном случае их комбинация возвращает значение **false**.

Битовые массивы должны иметь одинаковый размер для побитового сочетания функцией оператора-члена с помощью исключающего оператора `OR`.

#### <a name="example"></a>Пример

```cpp
// bitset_op_bitwiseOR.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;
   bitset<5> b1 ( 7 );
   bitset<5> b2 ( 11 );
   bitset<4> b3 ( 7 );

   cout << "The target bitset b1 is:    ( "<< b1 << " )." << endl;
   cout << "The parameter bitset b2 is: ( "<< b2 << " )." << endl;
   cout << endl;

   b1 ^= b2;
   cout << "After bitwise exclusive OR combination,\n"
        << "the target bitset b1 becomes:   ( "<< b1 << " )."
        << endl;

   // Note that the parameter-specified bitset in unchanged
   cout << "The parameter bitset b2 remains: ( "<< b2 << " )."
        << endl;

   // The following would cause an error because the bisets
   // must be of the same size to be combined
   // b1 |= b3;
}
```

```Output
The target bitset b1 is:    ( 00111 ).
The parameter bitset b2 is: ( 01011 ).

After bitwise exclusive OR combination,
the target bitset b1 becomes:   ( 01100 ).
The parameter bitset b2 remains: ( 01011 ).
```

### <a name="op_or_eq"></a> оператор&#124;=

Выполняет побитовое сочетание битовых массивов с использованием инклюзивной операции `OR`.

```cpp
bitset\<N>& operator|=(const bitset\<N>& right);
```

#### <a name="parameters"></a>Параметры

*Правильно*\
Битовый массив для побитового сочетания с целевым битовым массивом.

#### <a name="return-value"></a>Возвращаемое значение

Измененный целевой битовый массив, полученный в результате побитовой включающей операции `OR` с битовым массивом, указанным в качестве параметра.

#### <a name="remarks"></a>Примечания

Два бита, скомбинированные с помощью включающего оператора `OR`, возвращают значение **true**, если хотя бы один бит оценивается как **true**; если оба бита оцениваются как **false**, их комбинация возвращает значение **false**.

Битовые массивы должны иметь одинаковый размер для побитового сочетания функцией оператора-члена с помощью включающего оператора `OR`.

#### <a name="example"></a>Пример

```cpp
// bitset_op_BIO.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 7 );
   bitset<5> b2 ( 11 );
   bitset<4> b3 ( 7 );

   cout << "The target bitset b1 is:    ( "<< b1 << " )." << endl;
   cout << "The parameter bitset b2 is: ( "<< b2 << " )." << endl;
   cout << endl;

   b1 |= b2;
   cout << "After bitwise inclusive OR combination,\n"
        << "the target bitset b1 becomes:   ( "<< b1 << " )."
        << endl;

   // Note that the parameter-specified bitset in unchanged
   cout << "The parameter bitset b2 remains: ( "<< b2 << " )."
        << endl;

   // The following would cause an error because the bisets
   // must be of the same size to be combined
   // b1 |= b3;
}
```

```Output
The target bitset b1 is:    ( 00111 ).
The parameter bitset b2 is: ( 01011 ).

After bitwise inclusive OR combination,
the target bitset b1 becomes:   ( 01111 ).
The parameter bitset b2 remains: ( 01011 ).
```

### <a name="op_not"></a> оператор ~

Инвертирует все биты в целевом битовом массиве и возвращает результат.

```cpp
bitset\<N> operator~() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Битовый массив, все биты которого инвертированы по отношению к целевому битовому массиву.

#### <a name="example"></a>Пример

```cpp
// bitset_op_invert.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <bitset>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 7 );
   bitset<5> b2;
   b2 = ~b1;

   cout << "Bitset b1 is: ( "<< b1 << " )." << endl;
   cout << "Bitset b2 = ~b1 is: ( "<< b2 << " )." << endl;

   // These bits could also be flipped using the flip member function
   bitset<5> b3;
   b3 = b1.flip( );
   cout << "Bitset b3 = b1.flip( ) is: ( "<< b2 << " )." << endl;
}
```

```Output
Bitset b1 is: ( 00111 ).
Bitset b2 = ~b1 is: ( 11000 ).
Bitset b3 = b1.flip( ) is: ( 11000 ).
```

### <a name="reference"></a> Справочник по

Прокси-класс, предоставляющий ссылки на биты в битовом массиве, который используется для доступа к отдельным битам и их обработки в качестве вспомогательного класса для `operator[]` класса bitset.

```cpp
class reference {
   friend class bitset\<N>;
public:
   reference& operator=(bool val);
   reference& operator=(const reference& _Bitref);
   bool operator~() const;
   operator bool() const;
   reference& flip();
};
```

#### <a name="parameters"></a>Параметры

*Val*\
Значение объекта типа **bool** присвоить бита в битовом массиве.

*_Bitref*\
Ссылка в формате *x [i]* на бит в позиции *i* в битовом массиве *x*.

#### <a name="return-value"></a>Возвращаемое значение

Ссылка на бит в битовом массиве, заданный позицией аргумента для первой, второй и пятой функций — членов класса reference, и значение **true** или **false**, чтобы отразить значение измененного бита в массиве битов для третьей и четвертой функции — члена класса reference.

#### <a name="remarks"></a>Примечания

Класс `reference` существует только как вспомогательный класс для битового массива `operator[]`. Класс member описывает объект, который может получать доступ к отдельному биту в битовом массиве. Позвольте *b* быть объектом типа **bool**, *x* и *y* объектов типа **bitset\<**  *N* **>** , и *я* и *j* допустимые позиции внутри такого объекта. Обозначение *x [i]* ссылается на бит в позиции *i* в битовом массиве *x*. Функции — члены класса `reference` предоставляют по порядку следующие операции.

|Операция|Определение|
|---------------|----------------|
|*x*[*i*] = *b*|Магазины **bool** значение *b* в битовой позиции *я* в битовом массиве *x*.|
|*x*[*i*] = *y*[*j*]|Сохраняет значение бита *y*[*j*] в битовой позиции *i* в битовом массиве *x*.|
|*b* = ~ *x*[*i*]|Сохраняет инвертированное значение бита *x*[ *я*] в **bool** *b*.|
|*b* = *x*[*i*]|Сохраняет значение бита *x*[ *я*] в **bool** *b*.|
|*x*[*i*]. `flip`( )|Сохраняет инвертированное значение бита *x*[*i*] обратно в битовой позиции *i* в *x*.|

#### <a name="example"></a>Пример

```cpp
// bitset_reference.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 2 );
   bitset<5> b2 ( 6 );
   cout << "The initialized bitset<5> b1( 2 ) is: ( "<< b1 << " )."
        << endl;
   cout << "The initialized bitset<5> b2( 6 ) is: ( "<< b2 << " )."
        << endl;

   // Example of x [i] = b storing bool b at bit position i
   // in bitset x
   b1[ 0 ] = true;
   cout << "The bitset<5> b1 with the bit at position 0 set to 1"
        << "is: ( "<< b1 << " )" << endl;

   // Example of x [i] = y [j] storing the bool value of the
   // bit at position j in bitset y at bit position i in bitset x
   b2 [4] = b1 [0];      // b1 [0] = true
   cout << "The bitset<5> b2 with the bit at position 4 set to the "
        << "value\nof the bit at position 0 of the bit in "
        << "bitset<5> b1 is: ( "<<  b2  << " )" << endl;

   // Example of b = ~x [i] flipping the value of the bit at
   // position i of bitset x and storing the value in an
   // object b of type bool
   bool b = ~b2 [4];      // b2 [4] = false
   if ( b )
      cout << "The value of the object b = ~b2 [4] "
           << "of type bool is true." << endl;
   else
      cout << "The value of the object b = ~b2 [4] "
           << "of type bool is false." << endl;

   // Example of b = x [i] storing the value of the bit at
   // position i of bitset x in the object b of type bool
   b = b2 [4];
   if ( b )
      cout << "The value of the object b = b2 [4] "
           << "of type bool is true." << endl;
   else
      cout << "The value of the object b = b2 [4] "
           << "of type bool is false." << endl;

   // Example of x [i] . flip ( ) toggling the value of the bit at
   // position i of bitset x
   cout << "Before flipping the value of the bit at position 4 in "
        << "bitset b2,\nit is ( "<<  b2  << " )." << endl;
   b2 [4].flip( );
   cout << "After flipping the value of the bit at position 4 in "
        << "bitset b2,\nit becomes ( "<<  b2  << " )." << endl;
   bool c;
   c = b2 [4].flip( );
   cout << "After a second flip, the value of the position 4 "
        << "bit in b2 is now: " << c << ".";
}
```

```Output
The initialized bitset<5> b1( 2 ) is: ( 00010 ).
The initialized bitset<5> b2( 6 ) is: ( 00110 ).
The bitset<5> b1 with the bit at position 0 set to 1 is: ( 00011 )
The bitset<5> b2 with the bit at position 4 set to the value
of the bit at position 0 of the bit in bitset<5> b1 is: ( 10110 )
The value of the object b = ~b2 [4] of type bool is false.
The value of the object b = b2 [4] of type bool is true.
Before flipping the value of the bit at position 4 in bitset b2,
it is ( 10110 ).
After flipping the value of the bit at position 4 in bitset b2,
it becomes ( 00110 ).
After a second flip, the value of the position 4 bit in b2 is now: 1.
```

### <a name="reset"></a> Сброс

Сбрасывает все биты в битовом массиве в значение 0 или сбрасывает бит в указанной позиции в значение 0.

```cpp
bitset\<N>& reset();
bitset\<N>& reset(size_t _Pos);
```

#### <a name="parameters"></a>Параметры

*_Pos*\
Позиция бита в битовом массиве, который следует сбросить в 0.

#### <a name="return-value"></a>Возвращаемое значение

Копия битового массива, для которого была вызвана функция-член.

#### <a name="remarks"></a>Примечания

Вторая функция-член вызывает исключение [out_of_range](../standard-library/out-of-range-class.md), если указанная позиция больше, чем размер битового массива.

#### <a name="example"></a>Пример

```cpp
// bitset_reset.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 13 );
   cout << "The set of bits in bitset<5> b1(13) is: ( "<< b1 << " )"
        << endl;

   bitset<5> b1r3;
   b1r3 = b1.reset( 2 );
   cout << "The collecion of bits obtained from resetting the\n"
        << "third bit of bitset b1 is: ( "<< b1r3 << " )"
        << endl;

   bitset<5> b1r;
   b1r = b1.reset( );
   cout << "The collecion of bits obtained from resetting all\n"
        << "the elements of the bitset b1 is: ( "<< b1r << " )"
        << endl;
}
```

```Output
The set of bits in bitset<5> b1(13) is: ( 01101 )
The collecion of bits obtained from resetting the
third bit of bitset b1 is: ( 01001 )
The collecion of bits obtained from resetting all
the elements of the bitset b1 is: ( 00000 )
```

### <a name="set"></a> Набор

Устанавливает все биты в битовом массиве в значение 1 или устанавливает в значение 1 бит в указанной позиции.

```cpp
bitset\<N>& set();

bitset\<N>& set(
    size_t _Pos,
    bool val = true);
```

#### <a name="parameters"></a>Параметры

*_Pos*\
Позиция бита в битовом массиве, которому будет присваиваться значение.

*Val*\
Значение, присваиваемое биту в указанной позиции.

#### <a name="return-value"></a>Возвращаемое значение

Копия битового массива, для которого была вызвана функция-член.

#### <a name="remarks"></a>Примечания

Вторая функция-член вызывает исключение [out_of_range](../standard-library/out-of-range-class.md), если указанная позиция больше, чем размер битового массива.

#### <a name="example"></a>Пример

```cpp
// bitset_set.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 6 );
   cout << "The set of bits in bitset<5> b1(6) is: ( "<< b1 << " )"
        << endl;

   bitset<5> b1s0;
   b1s0 = b1.set( 0 );
   cout << "The collecion of bits obtained from setting the\n"
        << "zeroth bit of bitset b1 is: ( "<< b1s0 << " )"
        << endl;

   bitset<5> bs1;
   bs1 = b1.set( );
   cout << "The collecion of bits obtained from setting all the\n"
        << "elements of the bitset b1 is: ( "<< bs1 << " )"
        << endl;
}
```

```Output
The set of bits in bitset<5> b1(6) is: ( 00110 )
The collecion of bits obtained from setting the
zeroth bit of bitset b1 is: ( 00111 )
The collecion of bits obtained from setting all the
elements of the bitset b1 is: ( 11111 )
```

### <a name="size"></a> Размер

Возвращает количество бит в битовом массиве.

```cpp
size_t size() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Количество бит *N* в битовом массиве \<N>.

#### <a name="example"></a>Пример

```cpp
// bitset_size.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main()
{
    using namespace std;

    bitset<5> b1(6);
    size_t i;

    cout << "The set of bits in bitset<5> b1( 6 ) is: ( "<< b1 << " )"
         << endl;

    i = b1.size();

    cout << "The number of bits in bitset b1 is: " << i << "."
         << endl;
}
```

```Output
The set of bits in bitset<5> b1( 6 ) is: ( 00110 )
The number of bits in bitset b1 is: 5.
```

### <a name="test"></a> Тест

Проверяет, присвоено ли биту в указанной позиции в битовом массиве значение 1.

```cpp
bool test(size_t _Pos) const;
```

#### <a name="parameters"></a>Параметры

*_Pos*\
Позиция бита в битовом массиве, значение которого следует проверить.

#### <a name="return-value"></a>Возвращаемое значение

Значение **true**, если бит, заданный позицией в аргументе, имеет значение 1; в противном случае — значение **false**.

#### <a name="remarks"></a>Примечания

Функция-член вызывает исключение [out_of_range](../standard-library/out-of-range-class.md)

### <a name="to_string"></a> to_string

Преобразует объект битовом массиве в строковое представление.

```
template <class charT = char, class traits = char_traits<charT>, class Allocator = allocator<charT> >
   basic_string<charT, traits, Allocator> to_string(charT zero = charT('0'), charT one = charT('1')) const;
```

#### <a name="return-value"></a>Возвращаемое значение

Строковый объект из класса `basic_string`, где каждый бит в битовом массиве имеет соответствующий символ 1 и 0, если символ бит не определено.

#### <a name="example"></a>Пример

```cpp
// bitset_to_string.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 7 );

   cout << "The ordered set of bits in the bitset<5> b1( 7 )"
        << "\n  that was generated by the number 7 is: ( "
        << b1 << " )" << endl;

   string s1;
   s1 =  b1.template to_string<char, 
   char_traits<char>, allocator<char> >( );
   cout << "The string returned from the bitset b1"
        << "\n  by the member function to_string( ) is: "
        << s1 << "." << endl;
}
```

```Output
The ordered set of bits in the bitset<5> b1( 7 )
  that was generated by the number 7 is: ( 00111 )
The string returned from the bitset b1
  by the member function to_string( ) is: 00111.
```

### <a name="to_ullong"></a> to_ullong

Возвращает **long long без знака** задать значение, содержащее такой же бит как содержимое объекта bitset.

```
unsigned long long to_ullong() const;
```

#### <a name="return-value"></a>Возвращаемое значение

Возвращает сумму значений бит в битовой последовательности как **long long без знака**. Это **long long без знака** значение будет повторно создан такой же набор бит, если он используется для инициализации битовом массиве.

#### <a name="exceptions"></a>Исключения

Создает [overflow_error](overflow-error-class.md) объекта, если какой-либо бит в битовой последовательности бит имеет значение, которое нельзя представить в виде значения типа **long long без знака**.

#### <a name="remarks"></a>Примечания

Возвращает сумму значений бит в битовой последовательности как **long long без знака**.

### <a name="to_ulong"></a> to_ulong

Преобразует битовом целое число, которое бы получить последовательность его битов, если используется для инициализации битовый массив.

```
unsigned long to_ulong( ) const;
```

#### <a name="return-value"></a>Возвращаемое значение

Целое число, создаваемое биты в битовом массиве, если использовано в инициализации массива битов.

#### <a name="remarks"></a>Примечания

Применяя функцию-член возвращает целое число, которое имеет ту же последовательность цифр 1 и 0, как найти в последовательности битов в битовом массиве.

Функция-член создает [overflow_error](overflow-error-class.md) объекта, если какой-либо бит в битовой последовательности бит имеет значение, которое нельзя представить в виде значения типа **unsigned long**.

#### <a name="example"></a>Пример

```cpp
// bitset_to_ulong.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 7 );

   cout << "The ordered set of bits in the bitset<5> b1( 7 )"
        << "\n  that was generated by the number 7 is: ( "
        << b1 << " )" << endl;

   unsigned long int i;
   i = b1.to_ulong( );
   cout << "The integer returned from the bitset b1,"
        << "\n  by the member function to_long( ), that"
        << "\n  generated the bits as a base two number is: "
        << i << "." << endl;
}
```

```Output
The ordered set of bits in the bitset<5> b1( 7 )
  that was generated by the number 7 is: ( 00111 )
The integer returned from the bitset b1,
  by the member function to_long( ), that
  generated the bits as a base two number is: 7.
```
