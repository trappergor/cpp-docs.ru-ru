---
title: "Класс basic_ostream | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std::basic_ostream
- std.basic_ostream
- ostream/std::basic_ostream
- basic_ostream
dev_langs:
- C++
helpviewer_keywords:
- basic_ostream class
ms.assetid: 5baadc65-b662-4fab-8c9f-94457c58cda1
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 73cde54e382bb04b82739239bd0f07142c5b3321
ms.lasthandoff: 02/24/2017

---
# <a name="basicostream-class"></a>Класс basic_ostream
Этот класс шаблона описывает объект, управляющий вставкой элементов и закодированных объектов в буфер потока с элементами типа **Elem**, также известных как [char_type](../standard-library/basic-ios-class.md#basic_ios__char_type). Их признаки символов определяются классом **Tr**, также известным как [traits_type](../standard-library/basic-ios-class.md#basic_ios__traits_type).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class Elem, class Tr = char_traits<Elem>>  
class basic_ostream : virtual public basic_ios<Elem, Tr>  
```  
  
#### <a name="parameters"></a>Параметры  
 `Elem`  
 Объект `char_type`.  
  
 `Tr`  
 `traits_type` символа.  
  
## <a name="remarks"></a>Примечания  
 Большинство функций-членов, которые перегружают [operator<<](#basic_ostream__operator_lt__lt_),  — это форматированные выходные функции. Они следуют этому шаблону:  
  
```  
iostate state = goodbit;  
const sentry ok(*this);

if (ok)  
 {try  
 {<convert and insert elements  
    accumulate flags in state> }  
    catch (...)  
 {try  
 {setstate(badbit);

}  
    catch (...)  
 {}  
    if ((exceptions()& badbit) != 0)  
    throw; }}  
width(0);
// Except for operator<<(Elem)  
setstate(state);

return (*this);
```  
  
 Две другие функции-члены — это неформатированные выходные функции. Они следуют этому шаблону:  
  
```  
iostate state = goodbit;  
const sentry ok(*this);

if (!ok)  
    state |= badbit;  
else  
 {try  
 {<obtain and insert elements  
    accumulate flags in state> }  
    catch (...)  
 {try  
 {setstate(badbit);

}  
    catch (...)  
 {}  
    if ((exceptions()& badbit) != 0)  
    throw; }}  
setstate(state);

return (*this);
```  
  
 Обе группы функций вызывают [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)**(badbit)** при обнаружении ошибки вставки элементов.  
  
 Объект класса basic_istream\< **Elem**, **Tr**> хранит только виртуальный открытый базовый объект класса [basic_ios](../standard-library/basic-ios-class.md)**\<Elem**, **Tr>**.  
  
## <a name="example"></a>Пример  
 Дополнительные сведения о выходных потоках см. в примере для [класса basic_ofstream](../standard-library/basic-ofstream-class.md).  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[basic_ostream](#basic_ostream__basic_ostream)|Создает объект `basic_ostream`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[flush](#basic_ostream__flush)|Очищает буфер.|  
|[put](#basic_ostream__put)|Помещает символ в поток.|  
|[seekp](#basic_ostream__seekp)|Сбрасывает позицию в потоке вывода.|  
|[sentry](#basic_ostream__sentry)|Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные выходные функции.|  
|[swap](#basic_ostream__operator_eq)|Меняет местами значения в этом объекте `basic_ostream` и значения предоставленного объекта `basic_ostream`.|  
|[tellp](#basic_ostream__tellp)|Сообщает позицию в потоке вывода.|  
|[write](#basic_ostream__write)|Помещает символы в поток.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор=](#basic_ostream_operator_eq)|Присваивает значение указанного параметра объекта `basic_ostream` этому объекту.|  
|[оператор<<](#basic_ostream_operator_lt_lt_)|Записывает данные в поток.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** \<ostream>  
  
 **Пространство имен:** std  
  
##  <a name="a-namebasicostreambasicostreama--basicostreambasicostream"></a><a name="basic_ostream__basic_ostream"></a>  basic_ostream::basic_ostream  
 Создает объект `basic_ostream`.  
  
```  
explicit basic_ostream(
    basic_streambuf<Elem, Tr>* strbuf,  
    bool _Isstd = false);

basic_ostream(basic_ostream&& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` strbuf`  
 Объект типа [basic_streambuf](../standard-library/basic-streambuf-class.md).  
  
 `_Isstd`  
Значение  `true`, если это стандартный поток; в противном случае — значение `false`.  
  
 ` right`  
 Ссылка rvalue на объект типа `basic_ostream`.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует базовый класс путем вызова [init](../standard-library/basic-ios-class.md#basic_ios__init)(` strbuf`). Второй конструктор инициализирует базовый класс путем вызова [basic_ios::move](../standard-library/basic-ios-class.md#basic_ios__move)`(`` right``)`.  
  
### <a name="example"></a>Пример  
  Дополнительные сведения о выходных потоках см. в примере для [basic_ofstream::basic_ofstream](../standard-library/basic-ofstream-class.md#basic_ofstream__basic_ofstream).  
  
##  <a name="a-namebasicostreamflusha--basicostreamflush"></a><a name="basic_ostream__flush"></a>  basic_ostream::flush  
 Очищает буфер.  
  
```  
basic_ostream<Elem, Tr>& flush();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на объект basic_ostream.  
  
### <a name="remarks"></a>Примечания  
 Если [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf) не является пустым указателем, функция вызывает **rdbuf->**[pubsync](../standard-library/basic-streambuf-class.md#basic_streambuf__pubsync). Если возвращается значение –1, функция вызывает [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)(**badbit**). Она возвращает **\*this**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_ostream_flush.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout << "test";  
   cout.flush();  
}  
```  
  
```Output  
test  
```  
  
##  <a name="a-namebasicostreamoperatorltlta--basicostreamoperatorltlt"></a><a name="basic_ostream_operator_lt_lt_"></a> basic_ostream::operator&lt;&lt;  
 Записывает данные в поток.  
  
```  
basic_ostream<Elem, Tr>& operator<<(
    basic_ostream<Elem, Tr>& (* Pfn)(basic_ostream<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(
    ios_base& (* Pfn)(ios_base&));

basic_ostream<Elem, Tr>& operator<<(
    basic_ios<Elem, Tr>& (* Pfn)(basic_ios<Elem, Tr>&));

basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
basic_ostream<Elem, Tr>& operator<<(bool val);
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int __w64  val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long __w64  val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```  
  
### <a name="parameters"></a>Параметры  
 `Pfn`  
 Указатель функции.  
  
 ` strbuf`  
 Указатель на объект **stream_buf**.  
  
 ` val`  
 Элемент, записываемый в поток.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на объект basic_ostream.  
  
### <a name="remarks"></a>Примечания  
 Заголовок `<ostream>` также определяет несколько глобальных операторов вставки. Дополнительные сведения см. в разделе [operator<< (\<ostream>)](../standard-library/ostream-operators.md#operator_lt__lt_).  
  
 Первая функция-член обеспечивает, чтобы выражение в форме **ostr << endl** вызывало [endl](../standard-library/ostream-functions.md#endl)**(ostr)**, а затем возвращалось **\*this**. Вторая и третья функции обеспечивают аналогичное поведение других манипуляторов, таких как [hex](../standard-library/ios-functions.md#hex). Все остальные функции являются форматированными выходными функциями.  
  
 Функция  
  
```  
basic_ostream<Elem, Tr>& operator<<(basic_streambuf<Elem, Tr>* strbuf);
```  
  
 извлекает элементы из ` strbuf`, если ` strbuf`не является пустым указателем, и вставляет их. Извлечение останавливается в конце файла или если оно создает исключение (которое создается повторно). Оно также останавливается без извлечения соответствующего элемента, если вставка завершается неудачно. Если функция не вставляет элементы или если вставка создает исключение, эта функция вызывает [setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)(**failbit**). В любом случае эта функция возвращает **\*this**.  
  
 Функция  
  
```  
basic_ostream<Elem, Tr>& operator<<(bool val);
```  
  
 преобразует _`Val` в логическое поле и вставляет его путем вызова [use_facet](../standard-library/basic-filebuf-class.md#basic_filebuf__open)**<num_put\<Elem, OutIt>**`(`[getloc](../standard-library/ios-base-class.md#ios_base__getloc)). [put](#basic_ostream__put)(**OutIt**([rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)), **\*this**, `getloc`, **val**). Здесь **OutIt** определяется как [ostreambuf_iterator](../standard-library/ostreambuf-iterator-class.md)**\<Elem, Tr>**. Функция возвращает **\*this**.  
  
 Каждая из функций  
  
```  
basic_ostream<Elem, Tr>& operator<<(short val);
basic_ostream<Elem, Tr>& operator<<(unsigned short val);
basic_ostream<Elem, Tr>& operator<<(int val);
basic_ostream<Elem, Tr>& operator<<(unsigned int __w64  val);
basic_ostream<Elem, Tr>& operator<<(long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long val);
basic_ostream<Elem, Tr>& operator<<(long long val);
basic_ostream<Elem, Tr>& operator<<(unsigned long long val);
basic_ostream<Elem, Tr>& operator<<(const void* val);
```  
  
 преобразует ` val` в числовое поле и вставляет его путем вызова **use_facet<num_put\<Elem, OutIt>**(`getloc`). **put**(**OutIt**(`rdbuf`), **\*this**, `getloc`, **val**). Здесь **OutIt** определяется как **ostreambuf_iterator\<Elem, Tr>**. Функция возвращает **\*this**.  
  
 Каждая из функций  
  
```  
basic_ostream<Elem, Tr>& operator<<(float val);
basic_ostream<Elem, Tr>& operator<<(double val);
basic_ostream<Elem, Tr>& operator<<(long double val);
```  
  
 преобразует `val` в числовое поле и вставляет его путем вызова **use_facet<num_put\<Elem, OutIt>**(`getloc`)**. put**(**OutIt**(`rdbuf`), **\*this**, `getloc`, **val**). Здесь **OutIt** определяется как **ostreambuf_iterator\<Elem, Tr>**. Функция возвращает **\*this**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_ostream_op_write.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <string.h>  
  
using namespace std;  
  
ios_base& hex2( ios_base& ib )  
{  
   ib.unsetf( ios_base::dec );  
   ib.setf( ios_base::hex );  
   return ib;  
}  
  
basic_ostream<char, char_traits<char> >& somefunc(basic_ostream<char, char_traits<char> > &i)
{
    if (i == cout)
    {
        i << "i is cout" << endl;
    }
    return i;
}

class CTxtStreambuf : public basic_streambuf< char, char_traits< char > >
{
public:
    CTxtStreambuf(char *_pszText)
    {
        pszText = _pszText;
        setg(pszText, pszText, pszText + strlen(pszText));
    };
    char *pszText;
};

int main()
{
    cout << somefunc;
    cout << 21 << endl;

    hex2(cout);
    cout << 21 << endl;

    CTxtStreambuf f("text in streambuf");
    cout << &f << endl;
}
```  
  
##  <a name="a-namebasicostreamoperatoreqa--basicostreamoperator"></a><a name="basic_ostream__operator_eq"></a>  basic_ostream::operator=  
 Присваивает значения указанного параметра объекта `basic_ostream` этому объекту.  
  
```  
basic_ostream& operator=(basic_ostream&& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Ссылка `rvalue` на объект `basic_ostream`.  
  
### <a name="remarks"></a>Примечания  
 Оператор-член вызывает swap `(`` right``)`.  
  
##  <a name="a-namebasicostreamputa--basicostreamput"></a><a name="basic_ostream__put"></a>  basic_ostream::put  
 Помещает символ в поток.  
  
```  
basic_ostream<Elem, Tr>& put(char_type _Ch);
```  
  
### <a name="parameters"></a>Параметры  
 `_Ch`  
 Символ.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на объект basic_ostream.  
  
### <a name="remarks"></a>Примечания  
 Неформатированная выходная функция вставляет элемент `_Ch`. Она возвращает **\*this**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_ostream_put.cpp  
// compile with: /EHsc  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   cout.put( 'v' );  
   cout << endl;  
   wcout.put( L'l' );  
}  
```  
  
```Output  
v  
l  
```  
  
##  <a name="a-namebasicostreamseekpa--basicostreamseekp"></a><a name="basic_ostream__seekp"></a>  basic_ostream::seekp  
 Сбрасывает позицию в выходном потоке.  
  
```  
basic_ostream<Elem, Tr>& seekp(pos_type _Pos);

basic_ostream<Elem, Tr>& seekp(off_type _Off, ios_base::seekdir _Way);
```  
  
### <a name="parameters"></a>Параметры  
 `_Pos`  
 Позиция в потоке.  
  
 `_Off`  
 Смещение относительно `_Way`.  
  
 `_Way`  
 Одно из перечислений [ios_base::seekdir](../standard-library/ios-base-class.md#ios_base__seekdir).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на объект basic_ostream.  
  
### <a name="remarks"></a>Примечания  
 Если [fail](../standard-library/basic-ios-class.md#basic_ios__fail) имеет значение **false**, первая функция-член вызывает **newpos =** [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)**->** [pubseekpos](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekpos)(_*Pos*) для некоторых **newpos** временного объекта `pos_type`. Если **fail** имеет значение false, вторая функция-член вызывает **newpos = rdbuf->** [pubseekoff](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekoff)(*_Off, _Way*). В любом случае, если (`off_type`)**newpos ==** (`off_type`)(–1) (операция размещения завершается неудачно), функция вызывает **istr.**[setstate](../standard-library/basic-ios-class.md#basic_ios__setstate)(**failbit**). Обе функции возвращают **\*this**.  
  
### <a name="example"></a>Пример  
  
```cpp  
// basic_ostream_seekp.cpp  
// compile with: /EHsc  
#include <fstream>  
#include <iostream>  
  
int main()  
{  
    using namespace std;  
    ofstream x("basic_ostream_seekp.txt");  
    streamoff i = x.tellp();  
    cout << i << endl;  
    x << "testing";  
    i = x.tellp();  
    cout << i << endl;  
    x.seekp(2);   // Put char in third char position in file  
    x << " ";  
  
    x.seekp(2, ios::end);   // Put char two after end of file  
    x << "z";  
}  
```  
  
```Output  
0  
7  
```  
  
##  <a name="a-namebasicostreamsentrya--basicostreamsentry"></a><a name="basic_ostream__sentry"></a>  basic_ostream::sentry  
 Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные выходные функции.  
  
class sentry {  
   public:  
   explicit sentry(basic_ostream\<Elem, Tr>& _Ostr); operator bool() const; ~sentry(); };  
  
### <a name="remarks"></a>Примечания  
 Вложенный класс описывает объект, объявление которого структурирует форматированные и неформатированные выходные функции. Если **ostr.**[good](../standard-library/basic-ios-class.md#basic_ios__good) имеет значение **true**, и **ostr.**[tie](../standard-library/basic-ios-class.md#basic_ios__tie) не является пустым указателем, конструктор вызывает **ostr.tie->**[flush](#basic_ostream__flush). Затем конструктор сохраняет значение, возвращенное **ostr.good**, в объекте **status**. Последующий вызов **operator bool** предоставляет это сохраненное значение.  
  
 Если `uncaught_exception` возвращает **false** и [flags](../standard-library/ios-base-class.md#ios_base__flags) **&** [unitbuf](../standard-library/ios-functions.md#unitbuf) не равно нулю, деструктор вызывает [flush](#basic_ostream__flush).  
  
##  <a name="a-namebasicostreamswapa--basicostreamswap"></a><a name="basic_ostream__swap"></a>  basic_ostream::swap  
 Меняет местами значения в этом объекте `basic_ostream` и значения предоставленного объекта `basic_ostream`.  
  
```  
void swap(basic_ostream& right);
```  
  
### <a name="parameters"></a>Параметры  
 ` right`  
 Ссылка на объект `basic_ostream`.  
  
### <a name="remarks"></a>Примечания  
 Функция-член вызывает [basic_ios::swap](../standard-library/basic-ios-class.md#basic_ios__swap)`(`` right``)`, чтобы поменять местами содержимое этого объекта и содержимое ` right`.  
  
##  <a name="a-namebasicostreamtellpa--basicostreamtellp"></a><a name="basic_ostream__tellp"></a>  basic_ostream::tellp  
 Сообщает позицию в выходном потоке.  
  
```  
pos_type tellp();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Позиция в выходном потоке.  
  
### <a name="remarks"></a>Примечания  
 Если [fail](../standard-library/basic-ios-class.md#basic_ios__fail) имеет значение **false**, то функция-член возвращает [rdbuf](../standard-library/basic-ios-class.md#basic_ios__rdbuf)**->** [pubseekoff](../standard-library/basic-streambuf-class.md#basic_streambuf__pubseekoff)(0, `cur`, **in**). В противном случае она возвращает `pos_type`(–1).  
  
### <a name="example"></a>Пример  
  Пример использования `tellp` см. в разделе [seekp](#basic_ostream__seekp).  
  
##  <a name="a-namebasicostreamwritea--basicostreamwrite"></a><a name="basic_ostream__write"></a>  basic_ostream::write  
 Помещает символы в поток.  
  
```  
basic_ostream<Elem, Tr>& write(const char_type* str, streamsize count);
```  
  
### <a name="parameters"></a>Параметры  
 ` count`  
 Количество символов для помещения в поток.  
  
 ` str`  
 Символы для помещения в поток.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на объект basic_ostream.  
  
### <a name="remarks"></a>Примечания  
 [Неформатированная выходная функция](../standard-library/basic-ostream-class.md) вставляет последовательность элементов ` count`, начиная с ` str`.  
  
### <a name="example"></a>Пример  
  Пример использования `write` см. в разделе [streamsize](../standard-library/ios-typedefs.md#streamsize).  
  
## <a name="see-also"></a>См. также  
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Программирование iostream](../standard-library/iostream-programming.md)   
 [Соглашения iostreams](../standard-library/iostreams-conventions.md)


