---
title: "Класс money_get | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xlocmon/std::money_get"
  - "money_get"
  - "std.money_get"
  - "std::money_get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "money_get - класс"
ms.assetid: 692d3374-3fe7-4b46-8aeb-f8d91ed66b2e
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс money_get
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Шаблонный класс описывает объект, который можно использовать как аспект языкового стандарта для управления преобразованиями последовательностей типа `CharType` в денежные значения.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>  
class money_get : public locale::facet;
```  
  
#### <a name="parameters"></a>Параметры  
 `CharType`  
 Тип, используемый внутри программы для кодирования символов в языковом стандарте.  
  
 `InputIterator`  
 Тип итератора, из которого функции получения считывают своих входные данные.  
  
## <a name="remarks"></a>Примечания  
 Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **идентификатор.**  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[money_get](#money_get__money_get)|Конструктор для объектов типа `money_get`, используемых для извлечения числовых значений из последовательностей, представляющих денежные значения.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#money_get__char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|  
|[iter_type](#money_get__iter_type)|Тип, который описывает итератор ввода.|  
|[STRING_TYPE](#money_get__string_type)|Тип, описывающий строку, содержащую символы типа `CharType`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[do_get](#money_get__do_get)|Виртуальная функция, вызываемая для извлечения числового значения из последовательности символов, представляющей денежное значение.|  
|[Получить](#money_get__get)|Извлекает числовое значение из последовательности символов, представляющей денежное значение.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< языкового стандарта>  
  
 **Пространство имен:** std  
  
##  <a name="a-namemoneygetchartypea-moneygetchartype"></a><a name="money_get__char_type"></a>  money_get::char_type  
 Тип, используемый для описания символа, используемого языковым стандартом.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона **CharType**.  
  
##  <a name="a-namemoneygetdogeta-moneygetdoget"></a><a name="money_get__do_get"></a>  money_get::do_get  
 Виртуальная функция, вызываемая для извлекает числовое значение из последовательности символов, представляющую денежное значение.  
  
```
virtual iter_type do_get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const virtual iter_type do_get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    string_type& val) const
```  
  
### <a name="parameters"></a>Параметры  
 `first`  
 Входной итератор, начало последовательности для преобразования.  
  
 `last`  
 Итератор ввода, обращающийся к концу последовательность для преобразования.  
  
 `_Intl`  
 Логическое значение, указывающее тип символ валюты, ожидаемого в последовательности: **true** Если международные, **false** Если внутренние.  
  
 `_Iosbase`  
 Формат флаг, который при набор указывает, что символ валюты является необязательным. в противном случае оно является обязательным.  
  
 `_State`  
 Задает элементы соответствующие битовую маску для состояния потока согласно ли операции успешно или нет.  
  
 `val`  
 Строка, хранение преобразованных последовательности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор ввода первого элемента за пределами полей для ввода.  
  
### <a name="remarks"></a>Примечания  
 Первая функция защищенный виртуальный член пытается сопоставить последовательных элементов, начиная с первого в последовательности [ `first`, `last`) пока распознала полный, nonempty денежных поле ввода. Если успешно, он преобразует это поле в последовательность один или несколько десятичных цифр, при необходимости предшествует знак «минус» ( `–`), чтобы представить сумму и сохраняет результат в [string_type](#money_get__string_type) объекта `val`. Он возвращает итератор, обозначающие первого элемента за пределами полей для ввода. В противном случае, функция сохраняет пустую последовательность в `val` и задает `ios_base::failbit` в `_State`. Он возвращает итератор, обозначающие первого элемента за пределами любой префикс допустимых полей для ввода. В любом случае, если возвращаемое значение равно `last`, функция задает `ios_base::eofbit` в `_State`.  
  
 Вторая функция защищенный виртуальный член ведет себя таким же, как первый, за исключением того, что в случае успешного выполнения последовательности при необходимости десятичное число преобразуется в значение типа `long double` и сохраняет это значение в `val`.  
  
 Определяется формат полей для ввода [аспекта языкового стандарта](../standard-library/locale-class.md#facet_class)**ОС** возвращенное действующие [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [moneypunct](../Topic/moneypunct%20Class.md)\< **CharType**, **intl**>> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#ios_base__getloc)).  
  
 В частности:  
  
- **ОС**. [neg_format](../Topic/moneypunct%20Class.md#moneypunct__neg_format) определяет порядок, в котором расположены компоненты поля.  
  
- **ОС**. [curr_symbol](../Topic/moneypunct%20Class.md#moneypunct__curr_symbol) определяет последовательность элементов, составляющих символ валюты.  
  
- **ОС**. [positive_sign](../Topic/moneypunct%20Class.md#moneypunct__positive_sign) определяет последовательность элементов, служащий положительный знак.  
  
- **ОС**. [negative_sign](../Topic/moneypunct%20Class.md#moneypunct__negative_sign) определяет последовательность элементов, составляющих отрицательный знак.  
  
- **ОС**. [Группирование](../Topic/moneypunct%20Class.md#moneypunct__grouping) определяет способ группировки цифр слева от любого десятичного разделителя.  
  
- **ОС**. [thousands_sep](../Topic/moneypunct%20Class.md#moneypunct__thousands_sep) определяет элемент, разделяющую группы цифр слева от любого десятичного разделителя.  
  
- **ОС**. [decimal_point](../Topic/moneypunct%20Class.md#moneypunct__decimal_point) определяет элемент, разделяющую целое число цифр после запятой.  
  
- **ОС**. [frac_digits](../Topic/moneypunct%20Class.md#moneypunct__frac_digits) определяет количество цифр значительной доли справа от любого десятичного разделителя. При синтаксическом анализе Денежная сумма с нескольких цифр после запятой не вызываются для `frac_digits`, `do_get` прекращает разбор после использования более `frac_digits` символов.  
  
 Если строка знака ( **ОС**. `negative_sign` или **ОС**. `positive_sign`) имеет более одного элемента, только первый элемент соответствует где элемент равен **money_base::sign** отображается в шаблоне формата ( **ОС**. `neg_format`). В конце полей для ввода сопоставляются все оставшиеся элементы. Если ни одна из строк имеет первый элемент, который соответствует следующему элементу в денежном поле ввода, берется, как пустая строка знака и имеет положительный знак.  
  
 Если **iosbase**. [флаги](../standard-library/ios-base-class.md#ios_base__flags) & [showbase](../Topic/%3Cios%3E%20functions.md#showbase) не равно нулю, строка **ОС**. `curr_symbol` должен соответствовать where элемента, равного **money_base::symbol** отображается в шаблоне формата. В противном случае, если **money_base::symbol** происходит в конце шаблона формата, и если нет элементов строка знака по-прежнему совпадать, символ валюты не совпадает. В противном случае при необходимости сопоставляется символ валюты.  
  
 Если экземпляры **ОС**. `thousands_sep` происходят в части значения полей для ввода (где элемент равен **money_base::value** отображается в шаблоне формата), накладывается ограничение отсутствует группирования. В противном случае — группирование ограничения, накладываемые **ОС**. **Группирование** применяется принудительно. Примечание, результирующая последовательность цифр представляет собой целое число, младший **ОС**. `frac_digits` справа от десятичной запятой, считаются десятичными цифрами.  
  
 Соответствует произвольное число пробелов которой элемент равен **money_base::space** отображается в шаблоне формата, отличные от он отображается в конце шаблон формата. В противном случае — сопоставляется не внутренние пробелы. Элемент *ch* считается пробелы, если [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [ctype](../standard-library/ctype-class.md)\< **CharType**>> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#ios_base__getloc)). [—](../standard-library/ctype-class.md#ctype__is)( **ctype_base::space**, *ch*) является **true**.  
  
### <a name="example"></a>Пример  
  В примере показано [получить](#money_get__get), который вызывает метод `do_get`.  
  
##  <a name="a-namemoneygetgeta-moneygetget"></a><a name="money_get__get"></a>  money_get::Get  
 Извлекает числовое значение из последовательности символов, представляющей денежное значение.  
  
```
iter_type get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    long double& val) const;

iter_type get(iter_type first,
    iter_type last,
    bool _Intl,
    ios_base& _Iosbase,
    ios_base::iostate& _State,
    string_type& val) const;
```  
  
### <a name="parameters"></a>Параметры  
 `first`  
 Входной итератор, начало последовательности для преобразования.  
  
 `last`  
 Итератор ввода, обращающийся к концу последовательность для преобразования.  
  
 `_Intl`  
 Логическое значение, указывающее тип символ валюты, ожидаемого в последовательности: **true** Если международные, **false** Если внутренние.  
  
 `_Iosbase`  
 Формат флаг, который при набор указывает, что символ валюты является необязательным. в противном случае — является обязательным  
  
 `_State`  
 Задает элементы соответствующие битовую маску для состояния потока согласно ли успешной операции.  
  
 `val`  
 Строка, хранение преобразованных последовательности.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор ввода первого элемента за пределами полей для ввода.  
  
### <a name="remarks"></a>Примечания  
 Обе функции-члены возвращают [do_get](#money_get__do_get)( `first``,` `last``,` `_Intl`, `_Iosbase`, `_State`, `val`).  
  
### <a name="example"></a>Пример  
  
```  
// money_get_get.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
  
int main( )  
{  
   locale loc( "german_germany" );  
  
   basic_stringstream< char > psz;  
   psz << use_facet<moneypunct<char, 1> >(loc).curr_symbol() << "-1.000,56";  
   basic_stringstream< char > psz2;  
   psz2 << "-100056" << use_facet<moneypunct<char, 1> >(loc).curr_symbol();  
  
   ios_base::iostate st = 0;  
   long double fVal;  
  
   psz.flags( psz.flags( )|ios_base::showbase );   
   // Which forced the READING the currency symbol  
   psz.imbue(loc);  
   use_facet < money_get < char > >( loc ).  
      get( basic_istream<char>::_Iter( psz.rdbuf( ) ),     
           basic_istream<char>::_Iter( 0 ), true, psz, st, fVal );  
  
   if ( st & ios_base::failbit )  
      cout << "money_get(" << psz.str( ) << ", intl = 1) FAILED"  
           << endl;  
   else  
      cout << "money_get(" << psz.str( ) << ", intl = 1) = "   
           << fVal/100.0 << endl;  
  
   use_facet < money_get < char > >( loc ).  
      get(basic_istream<char>::_Iter(psz2.rdbuf( )),     
          basic_istream<char>::_Iter(0), false, psz2, st, fVal);  
  
   if ( st & ios_base::failbit )  
      cout << "money_get(" << psz2.str( ) << ", intl = 0) FAILED"   
           << endl;  
   else  
      cout << "money_get(" << psz2.str( ) << ", intl = 0) = "   
           << fVal/100.0 << endl;  
};  
```  
  
##  <a name="a-namemoneygetitertypea-moneygetitertype"></a><a name="money_get__iter_type"></a>  money_get::iter_type  
 Тип, который описывает итератор ввода.  
  
```
typedef InputIterator iter_type;
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона **InputIterator**.  
  
##  <a name="a-namemoneygetmoneygeta-moneygetmoneyget"></a><a name="money_get__money_get"></a>  money_get::money_get  
 Конструктор для объектов типа `money_get`, используемых для извлечения числовых значений из последовательностей, представляющих денежные значения.  
  
```
explicit money_get(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `_Refs`  
 Целочисленное значение используется для указания типа управление памятью для объекта.  
  
### <a name="remarks"></a>Примечания  
 Возможные значения параметра `_Refs` параметров и их важность являются:  
  
-   0: время существования объекта управляется национальных настроек, которые его содержат.  
  
-   1: время существования объекта должно осуществляться вручную.  
  
-   \> 0: эти значения не определены.  
  
 Нет прямого примеров будут невозможны, поскольку деструктор защищен.  
  
 Конструктор инициализирует свой базовый объект с **locale::**[аспекта](../standard-library/locale-class.md#facet_class)( **_***Refs*).  
  
##  <a name="a-namemoneygetstringtypea-moneygetstringtype"></a><a name="money_get__string_type"></a>  money_get::STRING_TYPE  
 Тип, который описывает строка, содержащая символы типа **CharType**.  
  
```
typedef basic_string<CharType, Traits, Allocator> string_type;
```  
  
### <a name="remarks"></a>Примечания  
 Тип, описывающий специализацию класса шаблона [basic_string](../standard-library/basic-string-class.md).  
  
## <a name="see-also"></a>См. также раздел  
 [\< языкового стандарта>](../standard-library/locale.md)   
 [Класс Facet](../standard-library/locale-class.md#facet_class)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)



