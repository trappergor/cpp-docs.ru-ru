---
title: "Функции &lt;iomanip&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iomanip/std::get_money
- iomanip/std::get_time
- iomanip/std::put_money
- iomanip/std::put_time
- iomanip/std::quoted
- iomanip/std::resetiosflags
- iomanip/std::setbase
- iomanip/std::setfill
- iomanip/std::setiosflags
- iomanip/std::setprecision
- iomanip/std::setw
ms.assetid: 3ddde610-70cc-4cfa-8a89-3e83d1d356a8
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d54e1d5071414f1e8f6ae96391aa1659397bbcb3
ms.lasthandoff: 02/24/2017

---
# <a name="ltiomanipgt-functions"></a>Функции &lt;iomanip&gt;
||||  
|-|-|-|  
|[get_money](#iomanip_get_money)|[get_time](#iomanip_get_time)|[put_money](#iomanip_put_money)|  
|[put_time](#iomanip_put_time)|[quoted](#quoted)|[resetiosflags](#resetiosflags)|  
|[setbase](#setbase)|[setfill](#setfill)|[setiosflags](#setiosflags)|  
|[setprecision](#setprecision)|[setw](#setw)|  
  
##  <a name="iomanip_get_money"></a>  get_money  
 Извлекает из потока денежное значение, используя нужный формат, и возвращает значение в параметре.  
  
```  
template <class Money>  
T7 get_money(Money& _Amount, bool _Intl);
```  
  
### <a name="parameters"></a>Параметры  
 _Amount  
 Извлеченное денежное значение.  
  
 _Intl  
 Если `true`, используется международный формат. Значение по умолчанию — `false`.  
  
### <a name="remarks"></a>Примечания  
 Манипулятор возвращает объект, который при извлечении из потока `str` ведет себя как `formatted input function`, вызывающий функцию-член `get` для ограничения языкового стандарта `money_get`, связанного с `str`, с использованием `_Intl` для указания международного формата. Если успешно, вызов сохраняет в `_Amount` извлеченное денежное значение. Затем манипулятор возвращает `str`.  
  
 `Money` должен иметь тип `long double` или быть экземпляром `basic_string` с теми же параметрами элемента и признаков, что и `str`.  
  
##  <a name="iomanip_get_time"></a>  get_time  
 Извлекает значение времени из потока, используя нужный формат. Возвращает значение в параметре в виде структуры времени.  
  
```  
template <class Elem>  
T10 put_time(struct tm *_Tptr, const Elem *_Fmt);
```  
  
### <a name="parameters"></a>Параметры  
 `_Tptr`  
 Время в виде структуры времени.  
  
 `_Fmt`  
 Требуемый формат для получения значения времени.  
  
### <a name="remarks"></a>Примечания  
 Манипулятор возвращает объект, который при извлечении из потока `str` ведет себя как `formatted input function`, вызывающий функцию-член `get` для ограничения языкового стандарта `time_get`, связанного с `str`, с использованием `tptr` для указания структуры времени и `fmt` для указания начала строки формата, завершающейся нулем. В случае успешного выполнения вызов хранит в структуре времени значения, связанные с полями извлеченного времени. Затем манипулятор возвращает `str`.  
  
##  <a name="iomanip_put_money"></a>  put_money  
 Вставляет денежную сумму в поток, используя нужный формат.  
  
```  
template <class Money>  
T8 put_money(const Money& _Amount, bool _Intl);
```  
  
### <a name="parameters"></a>Параметры  
 `_Amount`  
 Денежная сумма для вставки в поток.  
  
 `_Intl`  
 Значение `true`, если манипулятор должен использовать международный формат, и `false` в противном случае.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `str`.  
  
### <a name="remarks"></a>Примечания  
 Манипулятор возвращает объект, который при вставке в поток `str` ведет себя как форматированная выходная функция, вызывающая функцию-член `put` для ограничения языкового стандарта `money_put`, связанного с `str`. При успешном выполнении вызов вставляет `amount` в соответствующем формате, используя `_Intl` для указания международного формата и `str.fill()` в качестве элемента заполнения. Затем манипулятор возвращает `str`.  
  
 `Money` должен иметь тип `long double` или быть экземпляром `basic_string` с теми же параметрами элемента и признаков, что и `str`.  
  
##  <a name="iomanip_put_time"></a>  put_time  
 Записывает значение времени из структуры времени в поток с использованием указанного формата.  
  
```  
template <class Elem>  
T10 put_time(struct tm* _Tptr, const Elem* _Fmt);
```  
  
### <a name="parameters"></a>Параметры  
 `_Tptr`  
 Значение времени для записи в поток в виде структуры времени.  
  
 `_Fmt`  
 Требуемый формат для записи значения времени.  
  
### <a name="remarks"></a>Примечания  
 Манипулятор возвращает объект, который при вставке в поток `str` ведет себя как `formatted output function`. Функция вывода вызывает функцию-член `put` для ограничения языкового стандарта `time_put`, связанного с `str`. Функция вывода использует `_Tptr` для обозначения структуры времени и `_Fmt` для обозначения начала строки формата, оканчивающейся нулевым символом. В случае успешного выполнения вызов вставляет текст из строки формата и преобразованные значения из структуры времени. Затем манипулятор возвращает `str`.  
  
##  <a name="quoted"></a>  quoted  
 **(Новое в C++14)** Манипулятор iostream, который обеспечивает удобное обращение строк в потоки и из них с помощью операторов >> и <<.  
  
```  
quoted(std::string str) // or wstring  
quoted(const char* str) //or wchar_t* 
quoted(std::string str, char delimiter, char escape) // or wide versions  
quoted(const char* str, char delimiter, char escape) // or wide versions  
```  
  
### <a name="parameters"></a>Параметры  
 `str`  
 Std::string, char*, строковый литерал, необработанный строковый литерал или двухбайтовая версия любого из них (например, std::wstring, wchar_t\*).  
  
 `delimiter`  
 Указанный пользователем символ или двухбайтовый символ для использования в качестве разделителя для начала и конца строки.  
  
 `escape`  
 Указанный пользователем символ или двухбайтовый символ для использования в качестве escape-символа для escape-последовательностей в строке.  
  
### <a name="remarks"></a>Примечания  
 См. раздел [Использование операторов вставки и управление форматом](../standard-library/using-insertion-operators-and-controlling-format.md).  
  
### <a name="example"></a>Пример  
  В этом примере показано, как использовать `quoted` с разделителем по умолчанию и escape-символ с помощью узких строк. Широкие строки также поддерживаются.  
  
```cpp  
#include <iostream>  
#include <iomanip>  
#include <sstream>  
  
using namespace std;  
  
void show_quoted_v_nonquoted()  
{  
    // Results are identical regardless of input string type:  
    // string inserted { R"(This is a "sentence".)" }; // raw string literal  
    // string inserted { "This is a \"sentence\"." };  // regular string literal  
    const char* inserted = "This is a \"sentence\".";  // const char*  
    stringstream ss, ss_quoted;  
    string extracted, extracted_quoted;  
  
    ss << inserted;  
    ss_quoted << quoted(inserted);  
  
    cout << "ss.str() is storing       : " << ss.str() << endl;  
    cout << "ss_quoted.str() is storing: " << ss_quoted.str() << endl << endl;  
  
    // Round-trip the strings   
    ss >> extracted;  
    ss_quoted >> quoted(extracted_quoted);  
  
    cout << "After round trip: " << endl;  
    cout << "Non-quoted      : " << extracted << endl;  
    cout << "Quoted          : " << extracted_quoted << endl;  
}  
  
void main(int argc, char* argv[])  
{  
    show_quoted_v_nonquoted();  
  
    // Keep console window open in debug mode.  
    cout << endl << "Press Enter to exit" << endl;  
    string input{};  
    getline(cin, input);  
}  
  
/* Output:  
ss.str() is storing       : This is a "sentence".  
ss_quoted.str() is storing: "This is a \"sentence\"."  
  
After round trip:  
Non-quoted      : This  
Quoted          : This is a "sentence".  
  
Press Enter to exit  
*/  
```  
  
### <a name="example"></a>Пример  
  В следующем примере демонстрируется, как указать пользовательский разделитель или escape-символ:  
  
```cpp  
#include <iostream>  
#include <iomanip>  
#include <sstream>  
  
using namespace std;  
  
void show_custom_delimiter()  
{  
    string inserted{ R"("This" "is" "a" "heavily-quoted" "sentence".)" };  
    // string inserted{ "\"This\" \"is\" \"a\" \"heavily-quoted\" \"sentence\"" };  
    // const char* inserted{ "\"This\" \"is\" \"a\" \"heavily-quoted\" \"sentence\"" };  
    stringstream ss, ss_quoted;  
    string extracted;  
  
    ss_quoted << quoted(inserted, '*');  
    ss << inserted;  
    cout << "ss_quoted.str() is storing: " << ss_quoted.str() << endl;  
    cout << "ss.str() is storing       : " << ss.str() << endl << endl;  
  
    // Use the same quoted arguments as on insertion.  
    ss_quoted >> quoted(extracted, '*');  
  
    cout << "After round trip: " << endl;  
    cout << "Quoted          : " << extracted << endl;  
  
    extracted = {};  
    ss >> extracted;  
    cout << "Non-quoted      : " << extracted << endl << endl;  
}  
  
void show_custom_escape()  
{  
    string inserted{ R"(\\root\trunk\branch\nest\egg\yolk)" };  
    // string inserted{ "\\\\root\\trunk\\branch\\nest\\egg\\yolk" };  
    stringstream ss, ss_quoted, ss_quoted_custom;  
    string extracted;  
  
    // Use '"' as delimiter and '~' as escape character.  
    ss_quoted_custom << quoted(inserted, '"', '~');  
    ss_quoted << quoted(inserted);  
    ss << inserted;  
    cout << "ss_quoted_custom.str(): " << ss_quoted_custom.str() << endl;  
    cout << "ss_quoted.str()       : " << ss_quoted.str() << endl;  
    cout << "ss.str()              : " << ss.str() << endl << endl;  
  
    // No spaces in this string, so non-quoted behaves same as quoted  
    // after round-tripping.  
}  
  
void main(int argc, char* argv[])  
{  
    cout << "Custom delimiter:" << endl;  
    show_custom_delimiter();  
    cout << "Custom escape character:" << endl;  
    show_custom_escape();  
  
    // Keep console window open in debug mode.  
    cout << endl << "Press Enter to exit" << endl;  
    string input{};  
    getline(cin, input);  
}  
/* Output:  
Custom delimiter:  
ss_quoted.str() is storing: *"This" "is" "a" "heavily-quoted" "sentence".*  
ss.str() is storing       : "This" "is" "a" "heavily-quoted" "sentence".  
  
After round trip:  
Quoted          : "This" "is" "a" "heavily-quoted" "sentence".  
Non-quoted      : "This"  
  
Custom escape character:  
ss_quoted_custom.str(): "\\root\trunk\branch\nest\egg\yolk"  
ss_quoted.str()       : "\\\\root\\trunk\\branch\\nest\\egg\\yolk"  
ss.str()              : \\root\trunk\branch\nest\egg\yolk  
  
Press Enter to exit  
*/  
  
```  
  
##  <a name="resetiosflags"></a>  resetiosflags  
 Удаляет указанные флаги.  
  
```  
T1 resetiosflags(ios_base::fmtflags Mask);
```  
  
### <a name="parameters"></a>Параметры  
 `Mask`  
 Флажки, которые нужно очистить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Манипулятор возвращает объект, который при извлечении из потока **str** или при вставке в него вызывает **str**. [setf](../standard-library/ios-base-class.md#ios_base__setf)( `ios_base::`[fmtflags](../standard-library/ios-base-class.md#ios_base__fmtflags), _ *Mask*), а затем возвращает **str**.  
  
### <a name="example"></a>Пример  
  См. [setw](../standard-library/iomanip-functions.md#setw) для примера использования `resetiosflags`.  
  
##  <a name="setbase"></a>  setbase  
 Задает основание целых чисел.  
  
```  
T3 setbase(int _Base);
```  
  
### <a name="parameters"></a>Параметры  
 `_Base`  
 Основание числа.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Манипулятор возвращает объект, который при извлечении из потока **str** или при вставке в него вызывает **str**. `setf`( **mask**, [ios_base::basefield](../standard-library/ios-base-class.md#ios_base__fmtflags)), а затем возвращает **str**. В данном случае **mask** определяется так:  
  
-   Если _ *Base* имеет значение 8, то **mask** будет иметь значение `ios_base::`[oct](../standard-library/ios-functions.md#oct).  
  
-   Если _ *Base* имеет значение 10, то mask будет иметь значение `ios_base::`[dec](../standard-library/ios-functions.md#dec).  
  
-   Если _ *Base* имеет значение 16, то **mask** будет иметь значение `ios_base::`[hex](../standard-library/ios-functions.md#hex).  
  
-   Если _ *Base* имеет любое другое значение, то mask будет иметь значение `ios_base::`[fmtflags](../standard-library/ios-base-class.md#ios_base__fmtflags)(0).  
  
### <a name="example"></a>Пример  
  См. [setw](../standard-library/iomanip-functions.md#setw) для примера использования `setbase`.  
  
##  <a name="setfill"></a>  setfill  
 Задает символ, который будет использоваться для заполнения пробелов на экране с выравниванием по правому краю.  
  
```  
template <class Elem>  
T4 setfill(Elem Ch);
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Задает символ, который будет использоваться для заполнения пробелов при показе с выравниванием по правому краю.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Манипулятор шаблона возвращает объект, который при извлечении из потока **str** или при вставке в него вызывает **str**. [fill](../standard-library/basic-ios-class.md#basic_ios__fill)( `Ch`), а затем возвращает **str**. Тип **Elem** должен совпадать с типом элемента для потока **str**.  
  
### <a name="example"></a>Пример  
  См. [setw](../standard-library/iomanip-functions.md#setw) для примера использования `setfill`.  
  
##  <a name="setiosflags"></a>  setiosflags  
 Задает указанные флаги.  
  
```  
T2 setiosflags(ios_base::fmtflags Mask);
```  
  
### <a name="parameters"></a>Параметры  
 `Mask`  
 Флажки, которые нужно установить.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Манипулятор возвращает объект, который при извлечении из потока **str** или при вставке в него вызывает **str**. [setf](../standard-library/ios-base-class.md#ios_base__setf)(_ *Mask*), а затем возвращает **str**.  
  
### <a name="example"></a>Пример  
  См. [setw](../standard-library/iomanip-functions.md#setw) для примера использования `setiosflags`.  
  
##  <a name="setprecision"></a>  setprecision  
 Задает точность для значений с плавающей запятой.  
  
```  
T5 setprecision(streamsize Prec);
```  
  
### <a name="parameters"></a>Параметры  
 `Prec`  
 Точность для значений с плавающей запятой.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Манипулятор возвращает объект, который при извлечении из потока **str** или при вставке в него вызывает **str**. [precision](../standard-library/ios-base-class.md#ios_base__precision)( `Prec`), а затем возвращает **str**.  
  
### <a name="example"></a>Пример  
  См. [setw](../standard-library/iomanip-functions.md#setw) для примера использования `setprecision`.  
  
##  <a name="setw"></a>  setw  
 Ширина поля отображения для следующего элемента в потоке.  
  
```  
T6 setw(streamsize Wide);
```  
  
### <a name="parameters"></a>Параметры  
 `Wide`  
 Ширина поля отображения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Манипулятор возвращает объект, который при извлечении из потока **str** или при вставке в него вызывает **str**. [width](../standard-library/ios-base-class.md#ios_base__width)(_ *Wide*), а затем возвращает **str**.  
  
### <a name="remarks"></a>Примечания  
 Setw задает ширину только для следующего элемента в потоке и должен вставляться перед каждым элементом, ширину которого нужно задать.  
  
### <a name="example"></a>Пример  
  
```cpp  
// iomanip_setw.cpp   
// compile with: /EHsc  
// Defines the entry point for the console application.  
//  
// Sample use of the following manipulators:  
//   resetiosflags  
//   setiosflags  
//   setbase  
//   setfill  
//   setprecision  
//   setw  
  
#include <iostream>  
#include <iomanip>  
  
using namespace std;  
  
const double   d1 = 1.23456789;  
const double   d2 = 12.3456789;  
const double   d3 = 123.456789;  
const double   d4 = 1234.56789;  
const double   d5 = 12345.6789;  
const long      l1 = 16;  
const long      l2 = 256;  
const long      l3 = 1024;  
const long      l4 = 4096;  
const long      l5 = 65536;  
int         base = 10;  
  
void DisplayDefault( )  
{  
   cout << endl << "default display" << endl;  
   cout << "d1 = " << d1 << endl;  
   cout << "d2 = " << d2 << endl;  
   cout << "d3 = " << d3 << endl;  
   cout << "d4 = " << d4 << endl;  
   cout << "d5 = " << d5 << endl;  
}  
  
void DisplayWidth( int n )  
{  
   cout << endl << "fixed width display set to " << n << ".\n";  
   cout << "d1 = " << setw(n) << d1 << endl;  
   cout << "d2 = " << setw(n) << d2 << endl;  
   cout << "d3 = " << setw(n) << d3 << endl;  
   cout << "d4 = " << setw(n) << d4 << endl;  
   cout << "d5 = " << setw(n) << d5 << endl;  
}  
  
void DisplayLongs( )  
{  
   cout << setbase(10);  
   cout << endl << "setbase(" << base << ")" << endl;  
   cout << setbase(base);  
   cout << "l1 = " << l1 << endl;  
   cout << "l2 = " << l2 << endl;  
   cout << "l3 = " << l3 << endl;  
   cout << "l4 = " << l4 << endl;  
   cout << "l5 = " << l5 << endl;  
}  
  
int main( int argc, char* argv[] )  
{  
   DisplayDefault( );  
  
   cout << endl << "setprecision(" << 3 << ")" << setprecision(3);  
   DisplayDefault( );  
  
   cout << endl << "setprecision(" << 12 << ")" << setprecision(12);  
   DisplayDefault( );  
  
   cout << setiosflags(ios_base::scientific);  
   cout << endl << "setiosflags(" << ios_base::scientific << ")";  
   DisplayDefault( );  
  
   cout << resetiosflags(ios_base::scientific);  
   cout << endl << "resetiosflags(" << ios_base::scientific << ")";  
   DisplayDefault( );  
  
   cout << endl << "setfill('" << 'S' << "')" << setfill('S');  
   DisplayWidth(15);  
   DisplayDefault( );  
  
   cout << endl << "setfill('" << ' ' << "')" << setfill(' ');  
   DisplayWidth(15);  
   DisplayDefault( );  
  
   cout << endl << "setprecision(" << 8 << ")" << setprecision(8);  
   DisplayWidth(10);  
   DisplayDefault( );  
  
   base = 16;  
   DisplayLongs( );  
  
   base = 8;  
   DisplayLongs( );  
  
   base = 10;  
   DisplayLongs( );  
  
   return   0;  
}  
```  
  
```Output  
  
default display  
d1 = 1.23457  
d2 = 12.3457  
d3 = 123.457  
d4 = 1234.57  
d5 = 12345.7  
  
setprecision(3)  
default display  
d1 = 1.23  
d2 = 12.3  
d3 = 123  
d4 = 1.23e+003  
d5 = 1.23e+004  
  
setprecision(12)  
default display  
d1 = 1.23456789  
d2 = 12.3456789  
d3 = 123.456789  
d4 = 1234.56789  
d5 = 12345.6789  
  
setiosflags(4096)  
default display  
d1 = 1.234567890000e+000  
d2 = 1.234567890000e+001  
d3 = 1.234567890000e+002  
d4 = 1.234567890000e+003  
d5 = 1.234567890000e+004  
  
resetiosflags(4096)  
default display  
d1 = 1.23456789  
d2 = 12.3456789  
d3 = 123.456789  
d4 = 1234.56789  
d5 = 12345.6789  
  
setfill('S')  
fixed width display set to 15.  
d1 = SSSSS1.23456789  
d2 = SSSSS12.3456789  
d3 = SSSSS123.456789  
d4 = SSSSS1234.56789  
d5 = SSSSS12345.6789  
  
default display  
d1 = 1.23456789  
d2 = 12.3456789  
d3 = 123.456789  
d4 = 1234.56789  
d5 = 12345.6789  
  
setfill(' ')  
fixed width display set to 15.  
d1 =      1.23456789  
d2 =      12.3456789  
d3 =      123.456789  
d4 =      1234.56789  
d5 =      12345.6789  
  
default display  
d1 = 1.23456789  
d2 = 12.3456789  
d3 = 123.456789  
d4 = 1234.56789  
d5 = 12345.6789  
  
setprecision(8)  
fixed width display set to 10.  
d1 =  1.2345679  
d2 =  12.345679  
d3 =  123.45679  
d4 =  1234.5679  
d5 =  12345.679  
  
default display  
d1 = 1.2345679  
d2 = 12.345679  
d3 = 123.45679  
d4 = 1234.5679  
d5 = 12345.679  
  
setbase(16)  
l1 = 10  
l2 = 100  
l3 = 400  
l4 = 1000  
l5 = 10000  
  
setbase(8)  
l1 = 20  
l2 = 400  
l3 = 2000  
l4 = 10000  
l5 = 200000  
  
setbase(10)  
l1 = 16  
l2 = 256  
l3 = 1024  
l4 = 4096  
l5 = 65536  
```  
  
## <a name="see-also"></a>См. также  
 [\<iomanip>](../standard-library/iomanip.md)


