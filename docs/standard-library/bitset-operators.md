---
title: Операторы &lt;bitset&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- bitset/std::operator&amp;
- bitset/std::operator&gt;&gt;
- bitset/std::operator&lt;&lt;
- bitset/std::operator^
- bitset/std::operator|
dev_langs:
- C++
ms.assetid: 84fe6a13-6f6e-4cdc-bf8f-6f65ab1134d4
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::operator&amp; (bitset)
- std::operator&gt;&gt; (bitset)
- std::operator&lt;&lt; (bitset)
ms.workload:
- cplusplus
ms.openlocfilehash: 3056546e5a543c0058f789e293e0a63a3d53283a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850402"
---
# <a name="ltbitsetgt-operators"></a>Операторы &lt;bitset&gt;

||||
|-|-|-|
|[оператор&amp;](#op_amp)|[operator&gt;&gt;](#op_gt_gt)|[operator&lt;&lt;](#op_lt_lt)|
|[оператор^](#op_xor)|[оператор|](#op_or)|

## <a name="op_amp"></a> operator&amp;

Выполняет побитовую операцию `AND` между двумя битовыми массивами.

```cpp
template <size_t size>
bitset<size>
operator&(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух битовые массивы, соответствующие элементы должны объединяться с битовой операции `AND`.

`right` Второе из двух valarray, соответствующие элементы которого сами являются объединяются побитовым `AND`.

### <a name="return-value"></a>Возвращаемое значение

Битовый массив, элементы которого являются результатом выполнения операции `AND` с соответствующими элементами `left` и `right`.

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

## <a name="op_lt_lt"></a> operator&lt;&lt;

Вставляет текстовое представление битовой последовательности в поток вывода.

```

template <class CharType, class Traits, size_t N>
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& ostr,
    const bitset<N>& right);
```

### <a name="parameters"></a>Параметры

`right` Объект типа **bitset\<N >** , предназначенный для вставки в выходной поток в виде строки.

### <a name="return-value"></a>Возвращаемое значение

Текстовое представление битовой последовательности в **ostr**.

### <a name="remarks"></a>Примечания

Функция шаблона перегружает **operator<<**, позволяя записывать набор битов без предварительного преобразования в строку. Шаблонная функция фактически выполняется.

**ostr** << _ *Right*. [to_string](bitset-class.md) < **CharType**, **Traits**, **allocator**\< **CharType**> > ( )

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

## <a name="op_gt_gt"></a> operator&gt;&gt;

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

`_Istr` Строки, указанной во входной поток, вставляемый в битовом массиве.

`right` Битовый массив, который получает биты из входного потока.

### <a name="return-value"></a>Возвращаемое значение

Функция шаблона возвращает строку `_Istr`.

### <a name="remarks"></a>Примечания

Функция шаблона перегружает **operator>>** для сохранения в bitset _ *Right* значения bitset( `str`), где `str` является объектом типа [basic_string](basic-string-class.md) < **CharType**, **Traits**, **allocator**\< **CharType**> > **&** извлеченным из `_Istr`.

Функция шаблона извлекает элементы из `_Istr` и вставляет их в битовый массив до того, как:

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

## <a name="op_xor"></a>  оператор^

Выполняет побитовую операцию `EXCLUSIVE-OR` между двумя битовыми массивами.

```cpp
template <size_t size>
bitset<size>
operator^(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух битовые массивы, соответствующие элементы должны объединяться с битовой операции `EXCLUSIVE-OR`.

`right` Второе из двух valarray, соответствующие элементы которого сами являются объединяются побитовым `EXCLUSIVE-OR`.

### <a name="return-value"></a>Возвращаемое значение

Битовый массив, элементы которого являются результатом выполнения операции `EXCLUSIVE-OR` с соответствующими элементами `left` и `right`.

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

## <a name="op_or"></a>  оператор |

Выполняет побитовую операцию `OR` между двумя битовыми массивами.

```cpp
template <size_t size>
bitset<size>
operator|(
    const bitset<size>& left,
    const bitset<size>& right);
```

### <a name="parameters"></a>Параметры

`left` Первое из двух битовые массивы, соответствующие элементы должны объединяться с битовой операции `OR`.

`right` Второе из двух valarray, соответствующие элементы которого сами являются объединяются побитовым `OR`.

### <a name="return-value"></a>Возвращаемое значение

Битовый массив, элементы которого являются результатом выполнения операции `OR` с соответствующими элементами `left` и `right`.

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

## <a name="see-also"></a>См. также

[\<bitset>](../standard-library/bitset.md)<br/>
