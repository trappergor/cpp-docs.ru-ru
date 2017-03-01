---
title: "Класс ostream_iterator | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ostream_iterator
- std.ostream_iterator
- std::ostream_iterator
- iterator/std::ostream_iterator
dev_langs:
- C++
helpviewer_keywords:
- ostream_iterator class
ms.assetid: 24d842d3-9f45-4bf6-a697-62f5968f5a03
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 2d05749ba2837a3879c91886b9266de47dd2ece6
ms.openlocfilehash: 3542d4a47abc3616c00360f9885761d08de5e884
ms.lasthandoff: 02/24/2017

---
# <a name="ostreamiterator-class"></a>Класс ostream_iterator
Класс-шаблон ostream_iterator описывает объект итератора вывода, который записывает идущие подряд элементы в поток вывода с помощью оператора извлечения **<<**.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class Type class CharType = char class Traits = char_traits <CharType>>  
class ostream_iterator
```  
  
#### <a name="parameters"></a>Параметры  
 *Тип*  
 Тип объекта, который необходимо вставить в поток вывода.  
  
 `CharType`  
 Тип, представляющий шрифт символа для `ostream_iterator`. Этот аргумент является необязательным, значение по умолчанию — `char`*.*  
  
 `Traits`  
 Тип, представляющий шрифт символа для `ostream_iterator`. Этот аргумент является необязательным, значение по умолчанию — `char_traits`\< *CharType>.*  
  
 Класс ostream_iterator должен удовлетворять требованиям для итератора вывода. Алгоритмы можно записывать непосредственно в потоки вывода с помощью `ostream_iterator`.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[ostream_iterator](#ostream_iterator__ostream_iterator)|Создает `ostream_iterator`, инициализированный и разделенный для записи в поток вывода.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#ostream_iterator__char_type)|Тип, обеспечивающий тип символа для `ostream_iterator`.|  
|[ostream_type](#ostream_iterator__ostream_type)|Тип, обеспечивающий тип потока для `ostream_iterator`.|  
|[traits_type](#ostream_iterator__traits_type)|Тип, обеспечивающий тип признаков символа для `ostream_iterator`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор*](#ostream_iterator__operator_star)|Оператор разыменования, используемый для реализации выражения итератора вывода * `i` = `x`.|  
|[оператор++](#ostream_iterator__operator_add_add)|Нефункциональный оператор инкремента, возвращающий `ostream_iterator`, обращающийся к тому же объекту, к которому он обращался до вызова операции.|  
|[оператор=](#ostream_iterator__operator_eq)|Оператор присваивания, используемый для реализации выражения итератора вывода * `i` = `x` для записи в поток вывода.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<iterator>  
  
 **Пространство имен:** std  
  
##  <a name="a-nameostreamiteratorchartypea--ostreamiteratorchartype"></a><a name="ostream_iterator__char_type"></a>  ostream_iterator::char_type  
 Тип, обеспечивающий тип символа для итератора.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом для параметра-шаблона **Chartype**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// ostream_iterator_char_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   typedef ostream_iterator<int>::char_type CHT1;  
   typedef ostream_iterator<int>::traits_type CHTR1;  
  
   // ostream_iterator for stream cout  
   // with new line delimiter:  
    ostream_iterator<int, CHT1, CHTR1> intOut ( cout , "\n" );  
  
   // Standard iterator interface for writing  
   // elements to the output stream:  
   cout << "The integers written to the output stream\n"  
        << "by intOut are:" << endl;  
 *intOut = 10;  
 *intOut = 20;  
 *intOut = 30;  
}  
\* Output:   
The integers written to the output stream  
by intOut are:  
10  
20  
30  
*\  
```  
  
##  <a name="a-nameostreamiteratoroperatorstara--ostreamiteratoroperator"></a><a name="ostream_iterator__operator_star"></a>  ostream_iterator::operator*  
 Оператор разыменования, используемый для реализации выражения итератора вывода \* *ii* = *x*.  
  
```
ostream_iterator<Type, CharType, Traits>& operator*();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на `ostream_iterator`.  
  
### <a name="remarks"></a>Примечания  
 Требования для итератора вывода, которым должен удовлетворять `ostream_iterator`, требуют только допустимости выражения \* *ii* = *t* и сами по себе ничего не говорят об **операторе** или о `operator=`. Оператор-член в этой реализации возвращает **\*this**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// ostream_iterator_op_deref.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostream_iterator for stream cout  
   // with new line delimiter  
   ostream_iterator<int> intOut ( cout , "\n" );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *intOut = 10;  
   intOut++;      // No effect on iterator position  
 *intOut = 20;  
 *intOut = 30;  
}  
\* Output:   
Elements written to output stream:  
10  
20  
30  
*\  
```  
  
##  <a name="a-nameostreamiteratoroperatoraddadda--ostreamiteratoroperator"></a><a name="ostream_iterator__operator_add_add"></a>  ostream_iterator::operator++  
 Нефункциональный оператор инкремента, возвращающий `ostream_iterator`, обращающийся к тому же объекту, к которому он обращался до вызова операции.  
  
```
ostream_iterator<Type, CharType, Traits>& operator++();
ostream_iterator<Type, CharType, Traits> operator++(int);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на `ostream_iterator`.  
  
### <a name="remarks"></a>Примечания  
 Оба эти оператора-члена возвращают **\*this**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// ostream_iterator_op_incr.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostream_iterator for stream cout  
   // with new line delimiter  
   ostream_iterator<int> intOut ( cout , "\n" );  
  
   // standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *intOut = 10;  
   intOut++;      // No effect on iterator position  
 *intOut = 20;  
 *intOut = 30;  
}  
\* Output:   
Elements written to output stream:  
10  
20  
30  
*\  
```  
  
##  <a name="a-nameostreamiteratoroperatoreqa--ostreamiteratoroperator"></a><a name="ostream_iterator__operator_eq"></a>  ostream_iterator::operator=  
 Оператор присваивания, используемый для реализации выражения итератора вывода * `i` = `x` для записи в поток вывода.  
  
```
ostream_iterator<Type, CharType, Traits>& operator=(const Type& val);
```  
  
### <a name="parameters"></a>Параметры  
 `val`  
 Значение объекта типа `Type`, который нужно вставить в поток вывода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Оператор вставляет `val` в выходной поток, связанный с объектом, за которым следует разделитель, указанный в конструкторе [ostream_iterator](#ostream_iterator__ostream_iterator) (если он есть), а затем возвращает ссылку на `ostream_iterator`.  
  
### <a name="remarks"></a>Примечания  
 Требования для итератора вывода, которым должен удовлетворять `ostream_iterator`, требуют только допустимости выражения * `ii` = `t` и сами по себе ничего не говорят об операторе или об операторе=. Этот оператор-член возвращает `*this`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// ostream_iterator_op_assign.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostream_iterator for stream cout  
   // with new line delimiter  
   ostream_iterator<int> intOut ( cout , "\n" );  
  
   // Standard iterator interface for writing  
   // elements to the output stream  
   cout << "Elements written to output stream:" << endl;  
 *intOut = 10;  
   intOut++;      // No effect on iterator position  
 *intOut = 20;  
 *intOut = 30;  
}  
\* Output:   
Elements written to output stream:  
10  
20  
30  
*\  
```  
  
##  <a name="a-nameostreamiteratorostreamiteratora--ostreamiteratorostreamiterator"></a><a name="ostream_iterator__ostream_iterator"></a>  ostream_iterator::ostream_iterator  
 Создает `ostream_iterator`, инициализированный и разделенный для записи в поток вывода.  
  
```
ostream_iterator(
    ostream_type& _Ostr);

ostream_iterator(
    ostream_type& _Ostr,
    const CharType* _Delimiter);
```  
  
### <a name="parameters"></a>Параметры  
 `_Ostr`  
 Поток вывода типа [ostream_iterator::ostream_type](#ostream_iterator__ostream_type) для итерации по нему.  
  
 `_Delimiter`  
 Разделитель, который вставляется в поток вывода между значениями.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует указатель потока вывода значением `&_Ostr`. Указатель на строку разделителя обозначает пустую строку.  
  
 Второй конструктор инициализирует указатель потока вывода значением `&_Ostr`, а указатель строки разделителя значением `_Delimiter`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// ostream_iterator_ostream_iterator.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // ostream_iterator for stream cout  
   ostream_iterator<int> intOut ( cout , "\n" );  
 *intOut = 10;  
   intOut++;  
 *intOut = 20;  
   intOut++;  
  
   int i;  
   vector<int> vec;  
   for ( i = 1 ; i < 7 ; ++i )  
   {  
      vec.push_back (  i );  
   }  
  
   // Write elements to standard output stream  
   cout << "Elements output without delimiter: ";  
   copy ( vec.begin ( ), vec.end ( ),  
          ostream_iterator<int> ( cout ) );  
   cout << endl;  
  
   // Write elements with delimiter " : " to output stream  
   cout << "Elements output with delimiter: ";  
   copy ( vec.begin ( ), vec.end ( ),  
          ostream_iterator<int> ( cout, " : " ) );  
   cout << endl;  
}  
\* Output:   
10  
20  
Elements output without delimiter: 123456  
Elements output with delimiter: 1 : 2 : 3 : 4 : 5 : 6 :   
*\  
```  
  
##  <a name="a-nameostreamiteratorostreamtypea--ostreamiteratorostreamtype"></a><a name="ostream_iterator__ostream_type"></a>  ostream_iterator::ostream_type  
 Тип, обеспечивающий тип потока для итератора.  
  
```
typedef basic_ostream<CharType, Traits> ostream_type;
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом [basic_ostream](../standard-library/basic-ostream-class.md)< `CharType`, `Traits`>, класса потока в иерархии iostream, определяющего объекты, которые можно использовать для записи.  
  
### <a name="example"></a>Пример  
  См. раздел [ostream_iterator](#ostream_iterator__ostream_iterator) с примером объявления и использования `ostream_type`.  
  
##  <a name="a-nameostreamiteratortraitstypea--ostreamiteratortraitstype"></a><a name="ostream_iterator__traits_type"></a>  ostream_iterator::traits_type  
 Тип, обеспечивающий тип признаков символа итератора.  
  
```
typedef Traits traits_type;
```  
  
### <a name="remarks"></a>Примечания  
 Этот тип является синонимом для параметра-шаблона **Traits**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// ostream_iterator_traits_type.cpp  
// compile with: /EHsc  
#include <iterator>  
#include <vector>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
  
   // The following not OK, but are just the default values:  
   typedef ostream_iterator<int>::char_type CHT1;  
   typedef ostream_iterator<int>::traits_type CHTR1;  
  
   // ostream_iterator for stream cout  
   // with new line delimiter:  
    ostream_iterator<int, CHT1, CHTR1> intOut ( cout , "\n" );  
  
   // Standard iterator interface for writing  
   // elements to the output stream:  
   cout << "The integers written to output stream\n"  
        << "by intOut are:" << endl;  
 *intOut = 1;  
 *intOut = 10;  
 *intOut = 100;  
}  
\* Output:   
The integers written to output stream  
by intOut are:  
1  
10  
100  
*\  
```  
  
## <a name="see-also"></a>См. также  
 [\<iterator>](../standard-library/iterator.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Справочник по стандартной библиотеке C++](../standard-library/cpp-standard-library-reference.md)




