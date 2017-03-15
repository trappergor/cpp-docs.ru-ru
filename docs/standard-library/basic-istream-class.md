---
title: "Класс basic_istream | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- basic_istream
- istream/std::basic_istream
- std::basic_istream
- std.basic_istream
dev_langs:
- C++
helpviewer_keywords:
- basic_istream class
ms.assetid: c7c27111-de6d-42b4-95a3-a7e65259bf17
caps.latest.revision: 21
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
ms.sourcegitcommit: 85c900f2263ae1c1089478badc85388e3b5e8548
ms.openlocfilehash: 32308d4cd6a3cc1409f04958dde8dad9204718bc
ms.lasthandoff: 02/24/2017

---
# <a name="basicistream-class"></a>Класс basic_istream
Описывает объект, управляющий извлечением элементов и закодированных объектов из буфера потока с элементами типа `Elem`, также называемого [char_type](../standard-library/basic-ios-class.md#basic_ios__char_type). Их признаки символов определяются классом *Tr*, также называемым [traits_type](../standard-library/basic-ios-class.md#basic_ios__traits_type).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_istream : virtual public basic_ios<Elem, Tr>  
```  
  
## <a name="remarks"></a>Примечания  
 Большинство функций-членов, которые перегружают [оператор>>](#basic_istream__operator_gt__gt_), — это форматированные входные функции. Они следуют этому шаблону:  
  
```cpp  
iostate state = goodbit;
const sentry ok(*this);

if (ok)
{
    try
    {
        /*extract elements and convert
            accumulate flags in state.
            store a successful conversion*/
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);

return (*this);
```  
  
 Многие другие функции-члены — это неформатированные входные функции. Они следуют этому шаблону:  
  
```cpp  
iostate state = goodbit;
count = 0;    // the value returned by gcount  
const sentry ok(*this, true);

if (ok)
{
    try
    {
        /* extract elements and deliver
            count extracted elements in count
            accumulate flags in state */
    }
    catch (...)
    {
        try
        {
            setstate(badbit);

        }
        catch (...)
        {
        }
        if ((exceptions()& badbit) != 0)
            throw;
    }
}
setstate(state);
```  
  
 Обе группы функций вызывают [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **eofbit**) при обнаружении конца файла во время извлечения элементов.  
  
 Объект класса `basic_istream`< `Elem`, *Tr*> хранит:  
  
-   виртуальный открытый базовый объект класса [basic_ios](../standard-library/basic-ios-class.md)< `Elem`*Tr*> `.`;  
  
-   счетчик извлечений для последней операции неформатированного ввода (**count** в приведенном выше коде).  
  
## <a name="example"></a>Пример  
 Подробнее о входных потоках см. в примере для [класса basic_ifstream](../standard-library/basic-ifstream-class.md).  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[basic_istream](#basic_istream__basic_istream)|Создает объект типа `basic_istream`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[gcount](#basic_istream__gcount)|Возвращает число символов, считанных во время последнего неформатированного ввода.|  
|[get](#basic_istream__get)|Считывает один или несколько символов из входного потока.|  
|[getline](#basic_istream__getline)|Считывает строку из входного потока.|  
|[ignore](#basic_istream__ignore)|Пропускает несколько элементов после текущей позиции чтения.|  
|[peek](#basic_istream__peek)|Возвращает следующий символ для чтения.|  
|[putback](#basic_istream__putback)|Помещает указанный символ в поток.|  
|[read](#basic_istream__read)|Считывает указанное количество символов из потока и сохраняет их в массиве.|  
|[readsome](#basic_istream__readsome)|Чтение только из буфера.|  
|[seekg](#basic_istream__seekg)|Перемещает позицию чтения в потоке.|  
|[sentry](#basic_istream__sentry)|Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные входные функции.|  
|[swap](#basic_istream__swap)|Меняет местами этот объект `basic_istream` с указанным параметром объекта `basic_istream`.|  
|[sync](#basic_istream__sync)|Синхронизирует устройство ввода, связанное с потоком, с буфером потока.|  
|[tellg](#basic_istream__tellg)|Сообщает текущую позицию чтения в потоке.|  
|[unget](#basic_istream__unget)|Помещает самый последний считанный символ обратно в поток.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор>>](#basic_istream__operator_gt__gt_)|Вызывает функцию для входного потока или считывает форматированные данные из входного потока.|  
|[оператор=](#basic_istream__operator_eq)|Назначает `basic_istream` справа от оператора этому объекту. Это назначение перемещения с использованием ссылки `rvalue`, после которого не остается копии.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<istream>  
  
 **Пространство имен:** std  
  
##  <a name="a-namebasicistreambasicistreama--basicistreambasicistream"></a><a name="basic_istream__basic_istream"></a>  basic_istream::basic_istream  
 Создает объект типа `basic_istream`.  
  
```  
explicit basic_istream(
    basic_streambuf<Elem, Tr>* strbuf,  
    bool _Isstd = false);

basic_istream(basic_istream&& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` strbuf`  
 Объект типа [basic_streambuf](../standard-library/basic-streambuf-class.md).  
  
 `_Isstd`  
Значение  `true`, если это стандартный поток; в противном случае — значение `false`.  
  
 ` right`  
 Объект `basic_istream` для копирования.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует базовый класс путем вызова [init](../standard-library/basic-ios-class.md#basic_ios__init)(_S `trbuf`). Он также хранит нуль в счетчике извлечений. Дополнительные сведения об этом счетчике извлечений см. в разделе "Примечания" [класса basic_istream](../standard-library/basic-istream-class.md).  
  
 Второй конструктор инициализирует базовый класс путем вызова `move``( right)`. Он также сохраняет _R `ight.gcount()` в счетчике извлечений и сохраняет нуль в счетчике извлечений для _R `ight`.  
  
### <a name="example"></a>Пример  
  Дополнительные сведения о входных потоках см. в примере для [класса basic_ifstream](../standard-library/basic-ifstream-class.md#basic_ifstream__basic_ifstream).  
  
##  <a name="a-namebasicistreamgcounta--basicistreamgcount"></a><a name="basic_istream__gcount"></a>  basic_istream::gcount  
 Возвращает число символов, считанных во время последнего неформатированного ввода.  
  
```  
streamsize gcount() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Счетчик извлечений.  
  
### <a name="remarks"></a>Примечания  
 Используйте [basic_istream::get](#basic_istream__get) для чтения символов без форматирования.  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_istream_gcount.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   cout << "Type the letter 'a': ";  
  
   ws( cin );  
   char c[10];  
  
   cin.get( &c[0],9 );  
   cout << c << endl;  
  
   cout << cin.gcount( ) << endl;  
}  
```  
  
```Output  
  
a  
  
```  
  
```Output  
  
      aType the letter 'a':  
a  
1  
```  
  
##  <a name="a-namebasicistreamgeta--basicistreamget"></a><a name="basic_istream__get"></a>  basic_istream::get  
 Считывает один или несколько символов из входного потока.  
  
```  
int_type get();

basic_istream<Elem, Tr>& get(Elem& Ch);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count);
basic_istream<Elem, Tr>& get(Elem* str, streamsize count, Elem Delim);

basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf);
basic_istream<Elem, Tr>& get(basic_streambuf<Elem, Tr>& strbuf, Elem Delim);
```  
  
### <a name="parameters"></a>Параметры  
 ` count`  
 Число символов для чтения из `strbuf`.  
  
 `Delim`  
 Символ, который должен завершать чтение, если обнаруживается перед ` count`.  
  
 ` str`  
 Строка, в которую должна выполняться запись.  
  
 `Ch`  
 Символ для получения.  
  
 ` strbuf`  
 Буфер, в который должна выполняться запись.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Форма get без параметров возвращает чтение элементов как целое число либо конец файла. Прочие формы возвращают поток (* `this`).  
  
### <a name="remarks"></a>Примечания  
 Первая из этих неформатированных входных функций извлекает элемент, если это возможно, как при возврате `rdbuf` ->  `sbumpc`. В противном случае она возвращает **traits_type::**[eof](../standard-library/char-traits-struct.md#char_traits__eof). Если функция не извлекает ни один элемент, то вызывает [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**).  
  
 Вторая функция извлекает элемент [int_type](../standard-library/basic-ios-class.md#basic_ios__int_type) `meta` таким же образом. Если при сравнении `meta` оценивается как эквивалентный **traits_type::eof**, эта функция вызывает `setstate`( **failbit**). В противном случае она сохраняет **traits_type::**[to_char_type](../standard-library/char-traits-struct.md#char_traits__to_char_type)( `meta`) в `Ch`. Функция возвращает **\*this**.  
  
 Третья функция возвращает **get**(_ *Str*, ` count`, `widen`('\ **n**')).  
  
 Четвертая функция извлекает до ` count` - 1 элементов и сохраняет их в массив, начиная с _ *Str*. Она всегда сохраняет `char_type` после сохранения всех извлеченных элементов. В целях тестирования извлечение останавливается:  
  
-   в конце файла;  
  
-   после того как функция извлечет элемент, который оценивается как эквивалентный `Delim`, и в этом случае элемент возвращается в управляемую последовательность;  
  
-   после извлечения функцией ` count` - 1 элементов.  
  
 Если функция не извлекает ни один элемент, то она вызывает `setstate`( **failbit**). В любом случае она возвращает **\*this**.  
  
 Пятая функция возвращает **get**( **strbuf**, `widen`('\ **n**')).  
  
 Шестая функция извлекает элементы и вставляет их в **strbuf**. Извлечение останавливается в конце файла или на элементе, который при сравнении оценивается как эквивалентный _ *Delim,* и не извлекается. Оно также останавливается без извлечения соответствующего элемента, если вставка завершается неудачно или создает исключение (которое перехватывается, но не создается повторно). Если функция не извлекает ни один элемент, то она вызывает `setstate`( **failbit**). В любом случае эта функция возвращает **\*this**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_istream_get.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   char c[10];  
  
   c[0] = cin.get( );  
   cin.get( c[1] );  
   cin.get( &c[2],3 );  
   cin.get( &c[4], 4, '7' );  
  
   cout << c << endl;  
}  
```  
  
```Output  
  
1111  
```  
  
##  <a name="a-namebasicistreamgetlinea--basicistreamgetline"></a><a name="basic_istream__getline"></a>  basic_istream::getline  
 Получает строку из входного потока.  
  
```  
basic_istream<Elem, Tr>& getline(
    char_type* str,   
    streamsize count);

basic_istream<Elem, Tr>& getline(
    char_type* str,   
    streamsize count,   
    char_type Delim);
```  
  
### <a name="parameters"></a>Параметры  
 ` count`  
 Число символов для чтения из **strbuf**.  
  
 `Delim`  
 Символ, который должен завершать чтение, если обнаруживается перед ` count`.  
  
 ` str`  
 Строка, в которую должна выполняться запись.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток ( **\*this**).  
  
### <a name="remarks"></a>Примечания  
 Первая из этих неформатированных входных функций возвращает **getline**(_ *Str*, ` count`, `widen`(' `\`**n**')).  
  
 Вторая функция извлекает до ` count` - 1 элементов и сохраняет их в массив, начиная с _ *Str*. Она всегда сохраняет символ окончания строки после сохранения всех извлеченных элементов. В целях тестирования извлечение останавливается:  
  
-   в конце файла;  
  
-   после того как функция извлечет элемент, который оценивается как эквивалентный `Delim`, и в этом случае элемент не возвращается и не добавляется в управляемую последовательность;  
  
-   после извлечения функцией ` count` - 1 элементов.  
  
 Если функция не извлекает ни один элемент или извлекает ` count` - 1 элементов, она вызывает [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**). В любом случае она возвращает **\*this**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_istream_getline.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   char c[10];  
  
   cin.getline( &c[0], 5, '2' );  
   cout << c << endl;  
}  
```  
  
```Output  
  
121  
```  
  
##  <a name="a-namebasicistreamignorea--basicistreamignore"></a><a name="basic_istream__ignore"></a>  basic_istream::ignore  
 Пропускает несколько элементов после текущей позиции чтения.  
  
```  
basic_istream<Elem, Tr>& ignore(
    streamsize count = 1,  
    int_type Delim = traits_type::eof());
```  
  
### <a name="parameters"></a>Параметры  
 ` count`  
 Количество пропускаемых элементов от текущей позиции чтения.  
  
 `Delim`  
 Элемент, который, будучи обнаруженным до счетчика, приводит к возврату из **ignore** и разрешению чтения всех элементов, следующих за `Delim`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток ( **\*this**).  
  
### <a name="remarks"></a>Примечания  
 Неформатированная входная функция извлекает до ` count` элементов и удаляет их. Однако если ` count` равняется **numeric_limits\<int>::max**, то он считается произвольно большим. Извлечение останавливается раньше в конце файла или на элементе `Ch`, так что **traits_type::**[to_int_type](../standard-library/char-traits-struct.md#char_traits__to_int_type)( `Ch`) считается эквивалентным _ *Delim* (который также извлекается). Функция возвращает **\*this**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_istream_ignore.cpp  
// compile with: /EHsc  
#include <iostream>  
int main( )   
{  
   using namespace std;  
   char chararray[10];  
   cout << "Type 'abcdef': ";  
   cin.ignore( 5, 'c' );  
   cin >> chararray;  
   cout << chararray;  
}  
```  
  
```Output  
  
abcdef  
  
```  
  
```Output  
  
abcdefdef  
```  
  
##  <a name="a-namebasicistreamoperatorgtgta--basicistreamoperatorgtgt"></a><a name="basic_istream__operator_gt__gt_"></a>  basic_istream::operator&gt;&gt;
  
Вызывает функцию для входного потока или считывает форматированные данные из входного потока.  
    
```  
basic_istream& operator>>(basic_istream& (* Pfn)(basic_istream&));
basic_istream& operator>>(ios_base& (* Pfn)(ios_base&));
basic_istream& operator>>(basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));  
basic_istream& operator>>(basic_streambuf<Elem, Tr>* strbuf);
basic_istream& operator>>(bool& val);
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val);
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val);
basic_istream& operator>>(void *& val);
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```  
  
### <a name="parameters"></a>Параметры  
 `Pfn`  
 Указатель функции.  
  
 ` strbuf`  
 Объект типа **stream_buf**.  
  
 ` val`  
 Значение для чтения из потока.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток ( **\*this**).  
  
### <a name="remarks"></a>Примечания  
 Заголовок `<istream>` также определяет несколько глобальных операторов извлечения. Дополнительные сведения см. в разделе [оператор>> (\<istream>)](../standard-library/istream-operators.md#operator_gt__gt_).  
  
 Первая функция-член обеспечивает, чтобы выражение в форме **istr** >> `ws` вызывало [ws](../standard-library/istream-functions.md#ws)( **istr**), а затем возвращалось **\*this**. Вторая и третья функции обеспечивают аналогичное поведение других манипуляторов, таких как [hex](../standard-library/ios-functions.md#hex). Остальные функции — это форматированные входные функции.  
  
 Функция:  
  
```  
basic_istream& operator>>(
    basic_streambuf<Elem, Tr>* strbuf);
```  
  
 извлекает элементы, если _ *Strbuf* не является пустым указателем, и вставляет их в ` strbuf`. Извлечение останавливается в конце файла. Оно также останавливается без извлечения соответствующего элемента, если вставка завершается неудачно, или создает исключение (которое перехватывается, но не создается повторно). Если функция не извлекает ни один элемент, то вызывает [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**). В любом случае эта функция возвращает **\*this**.  
  
 Функция:  
  
```  
basic_istream& operator>>(bool& val);
```  
  
 извлекает поле и преобразует его в значение типа Boolean, вызывая [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open) < `num_get`\< **Elem**, **InIt**>( [getloc](../standard-library/ios-base-class.md#ios_base__getloc)). [get](../standard-library/ios-base-class.md#ios_base__getloc)( **InIt**( [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)), `Init`(0), **\*this**, `getloc`, ` val`). Здесь **InIt** задается как [istreambuf_iterator](../standard-library/istreambuf-iterator-class.md)\< **Elem**, **Tr**>. Функция возвращает **\*this**.  
  
 Каждая из следующих функций  
  
```  
basic_istream& operator>>(short& val);
basic_istream& operator>>(unsigned short& val);
basic_istream& operator>>(int& val);
basic_istream& operator>>(unsigned int& val);
basic_istream& operator>>(long& val);
basic_istream& operator>>(unsigned long& val); 
basic_istream& operator>>(long long& val);
basic_istream& operator>>(unsigned long long& val); 
basic_istream& operator>>(void *& val);
```  
  
 извлекает поле и преобразует его в числовое значение путем вызова `use_facet`< `num_get`\< **Elem**, **InIt**>( `getloc`). [get](#basic_istream__get)( **InIt**( `rdbuf`), `Init`(0), **\*this**, `getloc`, ` val`). Здесь **InIt** задается как `istreambuf_iterator`\< **Elem**, **Tr**>, и ` val` имеет тип **long***,*`unsigned long`* * или **void \***, в зависимости от того, что требуется.  
  
 Если преобразованное значение невозможно представить как тип ` val`, то функция вызывает [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**). В любом случае эта функция возвращает **\*this**.  
  
 Каждая из следующих функций  
  
```  
basic_istream& operator>>(float& val);
basic_istream& operator>>(double& val);
basic_istream& operator>>(long double& val);
```  
  
 извлекает поле и преобразует его в числовое значение путем вызова `use_facet`< `num_get`\< **Elem**, **InIt**>( `getloc`). **get**( **InIt**( `rdbuf`), `Init`(0), **\*this**, `getloc`, ` val`). Здесь **InIt** задается как `istreambuf_iterator`\< **Elem**, **Tr**>, и ` val` имеет тип **double** или `long double`, в зависимости от того, что требуется.  
  
 Если преобразованное значение невозможно представить как тип ` val`, то функция вызывает `setstate`( **failbit**). В любом случае она возвращает **\*this**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// istream_basic_istream_op_is.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
ios_base& hex2( ios_base& ib )   
{  
   ib.unsetf( ios_base::dec );  
   ib.setf( ios_base::hex );  
   return ib;  
}  
  
basic_istream<char, char_traits<char> >& somefunc(basic_istream<char, char_traits<char> > &i)  
{  
   if ( i == cin )   
   {  
      cerr << "i is cin" << endl;  
   }  
   return i;  
}  
  
int main( )   
{  
   int i = 0;  
   cin >> somefunc;  
   cin >> i;  
   cout << i << endl;  
   cin >> hex2;  
   cin >> i;  
   cout << i << endl;  
}  
```  
  
##  <a name="a-namebasicistreamoperatoreqa--basicistreamoperator"></a><a name="basic_istream__operator_eq"></a>  basic_istream::operator=  
 Назначает `basic_istream` справа от оператора этому объекту. Это назначение перемещения с использованием ссылки `rvalue`, после которого не остается копии.  
  
```  
basic_istream& operator=(basic_istream&& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Ссылка `rvalue` на объект `basic_ifstream`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает *this.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член вызывает swap `( right)`.  
  
##  <a name="a-namebasicistreampeeka--basicistreampeek"></a><a name="basic_istream__peek"></a>  basic_istream::peek  
 Возвращает следующий символ для чтения.  
  
```  
int_type peek();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Следующий символ для чтения.  
  
### <a name="remarks"></a>Примечания  
 Неформатированная входная функция извлекает элемент, если это возможно, как при возврате из `rdbuf` -> [sgetc](../standard-library/basic-streambuf-class.md#basic_streambuf__sgetc). В противном случае она возвращает **traits_type::**[eof](../standard-library/char-traits-struct.md#char_traits__eof).  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_istream_peek.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   char c[10], c2;  
   cout << "Type 'abcde': ";  
  
   c2 = cin.peek( );  
   cin.getline( &c[0], 9 );  
  
   cout << c2 << " " << c << endl;  
}  
```  
  
```Output  
  
abcde  
  
```  
  
```Output  
  
      abcdeType 'abcde': abcde  
a abcde  
```  
  
##  <a name="a-namebasicistreamputbacka--basicistreamputback"></a><a name="basic_istream__putback"></a>  basic_istream::putback  
 Помещает указанный символ в поток.  
  
```  
basic_istream<Elem, Tr>& putback(
    char_type Ch);
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Символ для помещения обратно в поток.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток ( **\*this**).  
  
### <a name="remarks"></a>Примечания  
 [Неформатированная входная функция](../standard-library/basic-istream-class.md) помещает обратно `Ch`, если это возможно, как при вызове [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)`->`[sputbackc](../standard-library/basic-streambuf-class.md#basic_streambuf__sputbackc). Если rdbuf является пустым указателем или вызов `sputbackc` возвращает **traits_type::**[eof](../standard-library/char-traits-struct.md#char_traits__eof), функция вызывает [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **badbit**). В любом случае она возвращает **\*this**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_istream_putback.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   char c[10], c2, c3;  
  
   c2 = cin.get( );  
   c3 = cin.get( );  
   cin.putback( c2 );  
   cin.getline( &c[0], 9 );  
   cout << c << endl;  
}  
```  
  
```Output  
  
qwq  
```  
  
##  <a name="a-namebasicistreamreada--basicistreamread"></a><a name="basic_istream__read"></a>  basic_istream::read  
 Считывает указанное количество символов из потока и сохраняет их в массиве.  
  
 Этот метод является потенциально опасным, так как зависит от вызывающего объекта при проверке правильности переданных значений.  
  
```  
basic_istream<Elem, Tr>& read(
    char_type* str,   
    streamsize count);
```  
  
### <a name="parameters"></a>Параметры  
 ` str`  
 Массив, из которого должны считываться символы.  
  
 ` count`  
 Число символов для чтения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток ( `*this`).  
  
### <a name="remarks"></a>Примечания  
 Неформатированная входная функция извлекает до `count` элементов и сохраняет их в массив, начиная с _ `Str`. Извлечение останавливается раньше в конце файла, в этом случае функция вызывает [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( `failbit`). В любом случае она возвращает `*this`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_istream_read.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main()  
{  
    char c[10];  
    int count = 5;  
  
    cout << "Type 'abcde': ";  
  
    // Note: cin::read is potentially unsafe, consider  
    // using cin::_Read_s instead.  
    cin.read(&c[0], count);  
    c[count] = 0;  
  
    cout << c << endl;  
}  
```  
  
```Output  
  
abcde  
  
```  
  
```Output  
  
      abcdeType 'abcde': abcde  
abcde  
```  
  
##  <a name="a-namebasicistreamreadsomea--basicistreamreadsome"></a><a name="basic_istream__readsome"></a>  basic_istream::readsome  
 Считывает указанное число значений символов.  
  
 Этот метод является потенциально опасным, так как зависит от вызывающего объекта при проверке правильности переданных значений.  
  
```  
streamsize readsome(
    char_type* str,  
    streamsize count);
```  
  
### <a name="parameters"></a>Параметры  
 `str`  
 Массив, в котором `readsome` сохраняет символы, которые считывает.  
  
 `count`  
 Число символов для чтения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Число фактически прочитанных символов [gcount](#basic_istream__gcount).  
  
### <a name="remarks"></a>Примечания  
 Эта неформатированная входная функция извлекает до `count` элементов и сохраняет их в массив `str`.  
  
 Эта функция не ожидает входных данных. Она считывает все доступные данные.  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_istream_readsome.cpp  
// compile with: /EHsc /W3  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   char c[10];  
   int count = 5;  
  
   cout << "Type 'abcdefgh': ";  
  
   // cin.read blocks until user types input.  
   // Note: cin::read is potentially unsafe, consider  
   // using cin::_Read_s instead.  
   cin.read(&c[0], 2);  
  
   // Note: cin::readsome is potentially unsafe, consider  
   // using cin::_Readsome_s instead.  
   int n = cin.readsome(&c[0], count);  // C4996  
   c[n] = 0;  
   cout << n << " characters read" << endl;  
   cout << c << endl;  
}  
```  
  
##  <a name="a-namebasicistreamseekga--basicistreamseekg"></a><a name="basic_istream__seekg"></a>  basic_istream::seekg  
 Перемещает позицию чтения в потоке.  
  
```  
basic_istream<Elem, Tr>& seekg(pos_type pos);

basic_istream<Elem, Tr>& seekg(off_type off, ios_base::seekdir way);
```  
  
### <a name="parameters"></a>Параметры  
 `pos`  
 Абсолютное положение, в которое следует переместить указатель чтения.  
  
 `off`  
 Смещение для перемещения указателя чтения относительно `way`.  
  
 `way`  
 Одно из перечислений [ios_base::seekdir](../standard-library/ios-base-class.md#ios_base__seekdir).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток ( **\*this**).  
  
### <a name="remarks"></a>Примечания  
 Первая функция-член выполняет как абсолютный поиск, вторая функция-член выполняет относительный поиск.  
  
> [!NOTE]
>  Не используйте вторую функцию-член с текстовыми файлами, так как стандартный C++ не поддерживает относительный поиск в текстовых файлах.  
  
 Если [fail](../standard-library/basic-ios-class.md#basic_ios__fail) имеет значение false, первая функция-член вызывает **newpos** = [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf) -> [pubseekpos](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekpos)( `pos`), для некоторых временных объектов **pos_type** **newpos**. Если **fail** имеет значение false, вторая функция-член вызывает **newpos** = **rdbuf** -> [pubseekoff](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekoff)( `off`, `way`). В любом случае, если ( `off_type`) **newpos** == ( `off_type`)(–1) (операция размещения завершается неудачно), функция вызывает **istr**. [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**). Обе функции возвращают **\*this**.  
  
 Если [fail](../standard-library/basic-ios-class.md#basic_ios__fail) имеет значение true, функции-члены не делают ничего.  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_istream_seekg.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main ( )   
{  
   using namespace std;  
   ifstream file;  
   char c, c1;  
  
   file.open( "basic_istream_seekg.txt" );  
   file.seekg(2);   // seek to position 2  
   file >> c;  
   cout << c << endl;  
}  
```  
  
##  <a name="a-namebasicistreamsentrya--basicistreamsentry"></a><a name="basic_istream__sentry"></a>  basic_istream::sentry  
 Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные входные функции.  
  
class sentry {  
   public:  
   explicit sentry( basic_istream\<Elem, Tr>& _Istr,  
   bool _Noskip = false); operator bool() const; };  
  
### <a name="remarks"></a>Примечания  
 Если `_Istr``.`[good](../standard-library/basic-ios-class.md#basic_ios__good) имеет значение true, то конструктор:  
  
-   Вызывает `_Istr`. [tie](../standard-library/basic-ios-class.md#basic_ios__tie) -> [flush](../standard-library/basic-ostream-class.md#basic_ostream__flush), если `_Istr`. `tie` не является пустым указателем.  
  
-   Эффективно вызывает [ws](../standard-library/istream-functions.md#ws)( `_Istr`), если `_Istr`. [flags](../standard-library/ios-base-class.md#ios_base__flags)**&**[skipws](../standard-library/ios-functions.md#skipws) не равно нулю.  
  
 Если после такой подготовки `_Istr`. **good** имеет значение false, то конструктор вызывает `_Istr`. [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **failbit**). В любом случае конструктор сохраняет значение, возвращенное `_Istr`. **good** в **status**. Последующий вызов **operator bool** предоставляет это сохраненное значение.  
  
##  <a name="a-namebasicistreamswapa--basicistreamswap"></a><a name="basic_istream__swap"></a>  basic_istream::swap  
 Меняет местами содержимое двух объектов `basic_istream`.  
  
```  
void swap(basic_istream& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Ссылка lvalue на объект `basic_istream`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция-член вызывает [basic_ios::swap](../standard-library/basic-ios-class.md#basic_ios__swap)`(`` right``)`. Она также обменивает количество извлечения с соответствующим значением для ` right`.  
  
##  <a name="a-namebasicistreamsynca--basicistreamsync"></a><a name="basic_istream__sync"></a>  basic_istream::sync  
 Синхронизирует устройство ввода, связанное с потоком, с буфером потока.  
  
```  
int sync();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf) является пустым указателем, функция возвращает значение –1. В противном случае она вызывает `rdbuf`  ->  [pubsync](../standard-library/basic-streambuf-class.md#basic_streambuf__pubsync). Если возвращается значение –1, функция вызывает [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **badbit**) и возвращает значение –1. В противном случае функция возвращает нуль.  
  
##  <a name="a-namebasicistreamtellga--basicistreamtellg"></a><a name="basic_istream__tellg"></a>  basic_istream::tellg  
 Сообщает текущую позицию чтения в потоке.  
  
```  
pos_type tellg();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Текущая позиция в потоке.  
  
### <a name="remarks"></a>Примечания  
 Если [fail](../standard-library/basic-ios-class.md#basic_ios__fail) имеет значение false, то функция-член возвращает [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf) -> [pubseekoff](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekoff)(0, `cur`, **in**). В противном случае она возвращает `pos_type`(–1).  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_istream_tellg.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <fstream>  
  
int main()  
{  
    using namespace std;  
    ifstream file;  
    char c;  
    streamoff i;  
  
    file.open("basic_istream_tellg.txt");  
    i = file.tellg();  
    file >> c;  
    cout << c << " " << i << endl;  
  
    i = file.tellg();  
    file >> c;  
    cout << c << " " << i << endl;  
}  
```  
  
##  <a name="a-namebasicistreamungeta--basicistreamunget"></a><a name="basic_istream__unget"></a>  basic_istream::unget  
 Помещает самый последний считанный символ обратно в поток.  
  
```  
basic_istream<Elem, Tr>& unget();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Поток ( **\*this**).  
  
### <a name="remarks"></a>Примечания  
 [Неформатированная входная функция](../standard-library/basic-istream-class.md) отправляет предыдущий элемент обратно в поток, если это возможно, как при вызове `rdbuf`  ->  [sungetc](../standard-library/basic-streambuf-class.md#basic_streambuf__sungetc). Если [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf) является пустым указателем или вызов `sungetc` возвращает **traits_type::**[eof](../standard-library/basic-ios-class.md#basic_ios__eof), функция вызывает [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)( **badbit**). В любом случае она возвращает **\*this**.  
  
 Сведения о том, как `unget` может завершиться ошибкой, см. в разделе [basic_streambuf::sungetc](../standard-library/basic-streambuf-class.md#basic_streambuf__sungetc).  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_istream_unget.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main( )   
{  
   char c[10], c2;  
  
   cout << "Type 'abc': ";  
   c2 = cin.get( );  
   cin.unget( );  
   cin.getline( &c[0], 9 );  
   cout << c << endl;  
}  
```  
  
```Output  
  
abc  
  
```  
  
```Output  
  
      abcType 'abc': abc  
abc  
```  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)


