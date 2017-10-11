---
title: "Операторы &lt;bitset&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- bitset/std::operator&amp;
- bitset/std::operator&gt;&gt;
- bitset/std::operator&lt;&lt;
- bitset/std::operator^
- bitset/std::operator|
dev_langs:
- C++
ms.assetid: 84fe6a13-6f6e-4cdc-bf8f-6f65ab1134d4
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
helpviewer_keywords:
- std::operator&amp; (bitset)
- std::operator&gt;&gt; (bitset)
- std::operator&lt;&lt; (bitset)
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 99e42dab27a7ee03c42e9b1b5a35e94cc7ed050b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="ltbitsetgt-operators"></a>Операторы &lt;bitset&gt;
||||  
|-|-|-|  
|[оператор&amp;](#op_amp)|[operator&gt;&gt;](#op_gt_gt)|[operator&lt;&lt;](#op_lt_lt)|  
|[оператор^](#op_xor)|[оператор|](#op_or)|  
  
##  <a name="op_amp"></a> operator&amp;  
 Выполняет побитовую операцию `AND` между двумя битовыми массивами.  
  
```  
template <size_t size>  
bitset<size>  
operator&(
    const bitset<size>& left,  
    const bitset<size>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Первый из двух битовых массивов, элементы которого должны объединяться с помощью побитовой операции `AND`.  
  
 `right`  
 Второй из двух массивов, элементы которого должны объединяться с помощью побитовой операции `AND`.  
  
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
  
##  <a name="op_lt_lt"></a>  оператор&lt;&lt;  
 Вставляет текстовое представление битовой последовательности в поток вывода.  
  
```  
 
template <class CharType, class Traits, size_t N>  
basic_ostream<CharType, Traits>& operator<<(
    basic_ostream<CharType, Traits>& ostr,  
    const bitset<N>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `right`  
 Объект типа **bitset\<N>**, который будет вставлен в выходной поток в виде строки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текстовое представление битовой последовательности в **ostr**.  
  
### <a name="remarks"></a>Примечания  
 Функция шаблона перегружает **operator<<**, позволяя записывать набор битов без предварительного преобразования в строку. Шаблонная функция фактически выполняется.  
  
 **ostr** << _ *Right*. [to_string](https://msdn.microsoft.com/library/2f93c55z.aspx) < **CharType**, **Traits**, **allocator**\< **CharType**> > ( )  
  
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
  
##  <a name="op_gt_gt"></a>  оператор&gt;&gt;  
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
 `_Istr`  
 Строка, которая вводится во входной поток для вставки в битовый массив.  
  
 `right`  
 Битовый массив, получающий биты из входного потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Функция шаблона возвращает строку `_Istr`.  
  
### <a name="remarks"></a>Примечания  
 Функция шаблона перегружает **operator>>** для сохранения в bitset _ *Right* значения bitset( `str`), где `str` является объектом типа [basic_string](https://msdn.microsoft.com/library/syxtdd4f.aspx) < **CharType**, **Traits**, **allocator**\< **CharType**> > **&** извлеченным из `_Istr`.  
  
 Функция шаблона извлекает элементы из `_Istr` и вставляет их в битовый массив до того, как:  
  
-   все битовые элементы будут извлечены из входного потока и сохранены в битовый массив;  
  
-   битовый массив заполнится битами из входного потока;  
  
-   встретится входной элемент, не являющийся ни 0, ни 1.  
  
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
  
##  <a name="op_xor"></a>  оператор^  
 Выполняет побитовую операцию `EXCLUSIVE-OR` между двумя битовыми массивами.  
  
```  
template <size_t size>  
bitset<size>  
operator^(
    const bitset<size>& left,  
    const bitset<size>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Первый из двух битовых массивов, элементы которого должны объединяться с помощью побитовой операции `EXCLUSIVE-OR`.  
  
 `right`  
 Второй из двух массивов, элементы которого должны объединяться с помощью побитовой операции `EXCLUSIVE-OR`.  
  
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
  
##  <a name="op_or"></a>оператор |  
 Выполняет побитовую операцию `OR` между двумя битовыми массивами.  
  
```  
template <size_t size>  
bitset<size>  
operator|(
    const bitset<size>& left,  
    const bitset<size>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Первый из двух битовых массивов, элементы которого должны объединяться с помощью побитовой операции `OR`.  
  
 `right`  
 Второй из двух массивов, элементы которого должны объединяться с помощью побитовой операции `OR`.  
  
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
 [\<bitset>](../standard-library/bitset.md)


