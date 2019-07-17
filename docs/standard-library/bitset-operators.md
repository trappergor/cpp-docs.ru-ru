---
title: Операторы &lt;bitset&gt;
ms.date: 11/04/2016
f1_keywords:
- bitset/std::operator&amp;
- bitset/std::operator&gt;&gt;
- bitset/std::operator&lt;&lt;
- bitset/std::operator^
- bitset/std::operator|
ms.assetid: 84fe6a13-6f6e-4cdc-bf8f-6f65ab1134d4
helpviewer_keywords:
- std::operator&amp; (bitset)
- std::operator&gt;&gt; (bitset)
- std::operator&lt;&lt; (bitset)
ms.openlocfilehash: 30367e003d2dad95e870854098e7fcae34f50efa
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243324"
---
# <a name="ltbitsetgt-operators"></a>Операторы &lt;bitset&gt;

## <a name="op_amp"></a> Оператор&amp;

Выполняет побитовую операцию `AND` между двумя битовыми массивами.

```cpp
template <size_t size>
bitset<size>
operator&(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Параметры

*Слева*\
Первый из двух битовых массивов, элементы которого должны объединяться с помощью побитовой операции `AND`.

*Правильно*\
Второй из двух массивов, элементы которого должны объединяться с помощью побитовой операции `AND`.

### <a name="return-value"></a>Возвращаемое значение

Битовый массив, элементы которого получены в результате выполнения `AND` операции на соответствующие элементы *левой* и *правой*.

### <a name="example"></a>Пример

```cpp
// bitset_and.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

using namespace std;

int main()
{
   bitset<4> b1 ( string("0101") );
   bitset<4> b2 ( string("0011") );
   bitset<4> b3 = b1 & b2;
   cout << "bitset 1: " << b1 << endl;
   cout << "bitset 2: " << b2 << endl;
   cout << "bitset 3: " << b3 << endl;
}
```

```Output
bitset 1: 0101
bitset 2: 0011
bitset 3: 0001
```

## <a name="op_lt_lt"></a> Оператор&lt;&lt;

Вставляет текстовое представление битовой последовательности в поток вывода.

```
template <class CharType, class Traits, size_t N>
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& ostr,
    const bitset<N>& right);
```

### <a name="parameters"></a>Параметры

*Правильно*\
Объект типа **bitset\<N>** , который будет вставлен в выходной поток в виде строки.

### <a name="return-value"></a>Возвращаемое значение

Текстовое представление битовой последовательности в `ostr`.

### <a name="remarks"></a>Примечания

Функция шаблона перегружает `operator<<`, позволяя битовом массиве были записаны без предварительного преобразования в строку. Шаблонная функция фактически выполняется.

**ostr** << _*справа*. [to_string](bitset-class.md) <**CharType**, **Traits**, **распределителя**\<**CharType**>>)

### <a name="example"></a>Пример

```cpp
// bitset_op_insert.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

int main( )
{
   using namespace std;

   bitset<5> b1 ( 9 );

   // bitset inserted into output stream directly
   cout << "The ordered set of bits in the bitset<5> b1(9)"
        << "\n can be output with the overloaded << as: ( "
        << b1 << " )" << endl;

   // Compare converting bitset to a string before
   // inserting it into the output steam
   string s1;
   s1 =  b1.template to_string<char,
      char_traits<char>, allocator<char> >( );
   cout << "The string returned from the bitset b1"
        << "\n by the member function to_string( ) is: "
        << s1 << "." << endl;
}
```

## <a name="op_gt_gt"></a> Оператор&gt;&gt;

Считывает строку битовых символов в битовый массив.

```
template <class CharType, class Traits, size_t Bits>
basic_istream<CharType, Traits>& operator>> (
    basic_istream<CharType, Traits>&
_Istr,
    bitset<N>&
    right);
```

### <a name="parameters"></a>Параметры

*_Istr*\
Строка, которая вводится во входной поток для вставки в битовый массив.

*Правильно*\
Битовый массив, получающий биты из входного потока.

### <a name="return-value"></a>Возвращаемое значение

Функция шаблона возвращает строку *_Istr*.

### <a name="remarks"></a>Примечания

Функция шаблона перегружает `operator>>` для сохранения в bitset _ *справа* битовом массиве значение (`str`), где `str` — это объект типа [basic_string](basic-string-class.md)  <  **CharType**, **Traits**, **распределителя** \< **CharType**>> **&** извлеченных из *_Istr*.

Функция шаблона извлекает элементы из *_Istr* и вставляет их в битовый массив до:

- все битовые элементы будут извлечены из входного потока и сохранены в битовый массив;

- битовый массив заполнится битами из входного потока;

- встретится входной элемент, не являющийся ни 0, ни 1.

### <a name="example"></a>Пример

```cpp
#include <bitset>
#include <iostream>
#include <string>

using namespace std;
int main()
{

   bitset<5> b1;
   cout << "Enter string of (0 or 1) bits for input into bitset<5>.\n"
        << "Try bit string of length less than or equal to 5,\n"
        << " (for example: 10110): ";
   cin >>  b1;

   cout << "The ordered set of bits entered from the "
        << "keyboard\n has been input into bitset<5> b1 as: ( "
        << b1 << " )" << endl;

   // Truncation due to longer string of bits than length of bitset
   bitset<2> b3;
   cout << "Enter string of bits (0 or 1) for input into bitset<2>.\n"
        << " Try bit string of length greater than 2,\n"
        << " (for example: 1011): ";
   cin >>  b3;

   cout << "The ordered set of bits entered from the "
        << "keyboard\n has been input into bitset<2> b3 as: ( "
        << b3 << " )" << endl;

   // Flushing the input stream
   char buf[100];
   cin.getline(&buf[0], 99);

   // Truncation with non-bit value
   bitset<5> b2;
   cout << "Enter a string for input into  bitset<5>.\n"
        << " that contains a character than is NOT a 0 or a 1,\n "
        << " (for example: 10k01): ";
   cin >>  b2;

   cout << "The string entered from the keyboard\n"
        << " has been input into bitset<5> b2 as: ( "
        << b2 << " )" << endl;
}
```

## <a name="op_xor"></a> оператор ^

Выполняет побитовую операцию `EXCLUSIVE-OR` между двумя битовыми массивами.

```cpp
template <size_t size>
bitset<size>
operator^(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Параметры

*Слева*\
Первый из двух битовых массивов, элементы которого должны объединяться с помощью побитовой операции `EXCLUSIVE-OR`.

*Правильно*\
Второй из двух массивов, элементы которого должны объединяться с помощью побитовой операции `EXCLUSIVE-OR`.

### <a name="return-value"></a>Возвращаемое значение

Битовый массив, элементы которого получены в результате выполнения `EXCLUSIVE-OR` операции на соответствующие элементы *левой* и *правой*.

### <a name="example"></a>Пример

```cpp
// bitset_xor.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

using namespace std;

int main()
{
   bitset<4> b1 ( string("0101") );
   bitset<4> b2 ( string("0011") );
   bitset<4> b3 = b1 ^ b2;
   cout << "bitset 1: " << b1 << endl;
   cout << "bitset 2: " << b2 << endl;
   cout << "bitset 3: " << b3 << endl;
}
```

```Output
bitset 1: 0101
bitset 2: 0011
bitset 3: 0110
```

## <a name="op_or"></a> оператор&#124;

Выполняет побитовую операцию `OR` между двумя битовыми массивами.

```cpp
template <size_t size>
bitset<size>
operator|(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Параметры

*Слева*\
Первый из двух битовых массивов, элементы которого должны объединяться с помощью побитовой операции `OR`.

*Правильно*\
Второй из двух массивов, элементы которого должны объединяться с помощью побитовой операции `OR`.

### <a name="return-value"></a>Возвращаемое значение

Битовый массив, элементы которого получены в результате выполнения `OR` операции на соответствующие элементы *левой* и *правой*.

### <a name="example"></a>Пример

```cpp
// bitset_or.cpp
// compile with: /EHsc
#include <bitset>
#include <iostream>
#include <string>

using namespace std;

int main()
{
   bitset<4> b1 ( string("0101") );
   bitset<4> b2 ( string("0011") );
   bitset<4> b3 = b1 | b2;
   cout << "bitset 1: " << b1 << endl;
   cout << "bitset 2: " << b2 << endl;
   cout << "bitset 3: " << b3 << endl;
}
```

```Output
bitset 1: 0101
bitset 2: 0011
bitset 3: 0111
```
