---
title: "Класс money_put | Microsoft Docs"
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
  - "std::money_put"
  - "xlocmon/std::money_put"
  - "money_put"
  - "std.money_put"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "money_put - класс"
ms.assetid: f439fd56-c9b1-414c-95e1-66c918c6eee6
caps.latest.revision: 19
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс money_put
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Шаблонный класс описывает объект, который можно использовать как аспект языкового стандарта для управления преобразованиями денежных значений в последовательности типа `CharType`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class CharType,  
    class OutputIterator = ostreambuf_iterator<CharType>>  
class money_put : public locale::facet;  
```  
  
#### <a name="parameters"></a>Параметры  
 `CharType`  
 Тип, используемый внутри программы для кодирования символов в языковом стандарте.  
  
 `OutputIterator`  
 Тип итератора, куда функции записи денежных значений записывают свои выходные данные.  
  
## <a name="remarks"></a>Примечания  
 Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **идентификатор.**  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[money_put](#money_put__money_put)|Конструктор для объектов типа `money_put`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#money_put__char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|  
|[iter_type](#money_put__iter_type)|Тип, который описывает итератор вывода.|  
|[STRING_TYPE](#money_put__string_type)|Тип, описывающий строку, содержащую символы типа `CharType`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[do_put](#money_put__do_put)|Виртуальная функция, вызываемая для преобразования числа или строки в последовательность символов, представляющую денежное значение.|  
|[PUT](#money_put__put)|Преобразует число или строку в последовательность символов, представляющую денежное значение.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< языкового стандарта>  
  
 **Пространство имен:** std  
  
##  <a name="a-namemoneyputchartypea-moneyputchartype"></a><a name="money_put__char_type"></a>  money_put::char_type  
 Тип, используемый для описания символа, используемого языковым стандартом.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона **CharType**.  
  
##  <a name="a-namemoneyputdoputa-moneyputdoput"></a><a name="money_put__do_put"></a>  money_put::do_put  
 Виртуальная функция, вызываемая для преобразования числа или строки в последовательность символов, представляющую денежное значение.  
  
```  
virtual iter_type do_put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,   
    const string_type& val) const;

 
virtual iter_type do_put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,  
    long double val) const;
```  
  
### <a name="parameters"></a>Параметры  
 ` next`  
 Итератор, обращающийся к первому элементу вставленной строки.  
  
 `_Intl`  
 Логическое значение, указывающее тип символ валюты, ожидаемого в последовательности: **true** Если международные, **false** Если внутренние.  
  
 `_Iosbase`  
 Формат флаг, который при набор указывает, что символ валюты является необязательным. в противном случае — является обязательным  
  
 `_Fill`  
 Символ, используемый для интервала.  
  
 ` val`  
 Строковый объект для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор вывода полученных адресов на позицию после последнего элемента.  
  
### <a name="remarks"></a>Примечания  
 Первая функция защищенный виртуальный член создает последовательных элементов, начиная с ` next` для получения вывода денежных значений поля из [string_type](#money_put__string_type) объекта ` val`. Последовательности, контролируемой ` val` должен начинаться с одного или нескольких десятичных цифр, при необходимости предшествует знак минуса (-), который представляет объем. Функция возвращает итератор, назначение первого элемента за пределами поля денежных выходные данные.  
  
 Вторая функция защищенный виртуальный член ведет себя так же как и первая, за исключением, что он фактически первый преобразует ` val` последовательность десятичных цифр, при необходимости предшествует знак минуса, затем преобразует этой последовательности, как описано выше.  
  
 Формат вывода денежных значений определяется [аспекта языкового стандарта](../standard-library/locale-class.md#facet_class) ОС, возвращенный вызовом (при наличии) [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [moneypunct](../Topic/moneypunct%20Class.md)\< **CharType**, **intl**>> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#ios_base__getloc)).  
  
 В частности:  
  
- **ОС**. [pos_format](../Topic/moneypunct%20Class.md#moneypunct__pos_format) определяет порядок, в котором компоненты поля создаются автоматически неотрицательное значение.  
  
- **ОС**. [neg_format](../Topic/moneypunct%20Class.md#moneypunct__neg_format) определяет порядок, в котором компоненты поля создаются автоматически отрицательное значение.  
  
- **ОС**. [curr_symbol](../Topic/moneypunct%20Class.md#moneypunct__curr_symbol) определяет последовательность элементов, для создания для символа валюты.  
  
- **ОС**. [positive_sign](../Topic/moneypunct%20Class.md#moneypunct__positive_sign) определяет последовательность элементов на генерацию положительный знак.  
  
- **ОС**. [negative_sign](../Topic/moneypunct%20Class.md#moneypunct__negative_sign) определяет последовательность элементов на генерацию отрицательный знак.  
  
- **ОС**. [Группирование](../Topic/moneypunct%20Class.md#moneypunct__grouping) определяет способ группировки цифр слева от любого десятичного разделителя.  
  
- **ОС**. [thousands_sep](../Topic/moneypunct%20Class.md#moneypunct__thousands_sep) определяет элемент, разделяющую группы цифр слева от любого десятичного разделителя.  
  
- **ОС**. [decimal_point](../Topic/moneypunct%20Class.md#moneypunct__decimal_point) определяет элемент, который отделяет целочисленных цифр от любого цифр после запятой.  
  
- **ОС**. [frac_digits](../Topic/moneypunct%20Class.md#moneypunct__frac_digits) определяет количество цифр значительной доли справа от любого десятичного разделителя.  
  
 Если строка знака ( **ОС**. `negative_sign` или **ОС**. `positive_sign`) имеет более одного элемента, только первый элемент создается, когда элемент равен **money_base::sign** отображается в шаблоне формата ( **ОС**. `neg_format` или **ОС**. `pos_format`). Все оставшиеся элементы создаются в конце вывода денежных значений поля.  
  
 Если **iosbase**. [флаги](../standard-library/ios-base-class.md#ios_base__flags) & [showbase](../Topic/%3Cios%3E%20functions.md#showbase) не равно нулю, строка **ОС**. `curr_symbol` создается, когда элемент равен **money_base::symbol** отображается в шаблоне формата. В противном случае создается без символа валюты.  
  
 Если накладываемые без ограничений группирования **ОС**. **Группирование** (первый элемент имеет значение CHAR_MAX), затем экземпляры **ОС**. `thousands_sep` создаются в части значения полей вывода денежных значений (где элемент равен **money_base::value** отображается в шаблоне формата). Если **ОС**. `frac_digits` — ноль, а затем не экземпляр **ОС**. `decimal_point` создается после десятичных цифр. В противном случае — результирующего вывода денежных значений поля помещает низкого порядка **ОС**. `frac_digits` десятичные цифры справа от десятичной запятой.  
  
 Происходит заполнение, как и для любого поля вывод в числовом формате, за исключением того, что если **iosbase**. **флаги** & **iosbase**. [Внутренняя](../Topic/%3Cios%3E%20functions.md#internal) имеет ненулевое значение, все внутренние поля создается, когда элемент равен **money_base::space** отображается в шаблоне формата, если оно отображается. В противном случае — внутреннее заполнение предшествует создаваемой последовательности. Символ заполнения **заполнения**.  
  
 Вызовы функций **iosbase**. **Ширина**(0), чтобы ширина поля равным нулю.  
  
### <a name="example"></a>Пример  
  В примере показано [поместить](#money_put__put), где виртуальная функция-член вызывается **поместить**.  
  
##  <a name="a-namemoneyputitertypea-moneyputitertype"></a><a name="money_put__iter_type"></a>  money_put::iter_type  
 Тип, который описывает итератор вывода.  
  
```  
typedef OutputIterator iter_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона **OutputIterator.**  
  
##  <a name="a-namemoneyputmoneyputa-moneyputmoneyput"></a><a name="money_put__money_put"></a>  money_put::money_put  
 Конструктор для объектов типа `money_put`.  
  
```  
explicit money_put(size_t _Refs = 0);
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
  
 Конструктор инициализирует свой базовый объект с **locale::**[аспекта](../standard-library/locale-class.md#facet_class)( `_Refs`).  
  
##  <a name="a-namemoneyputputa-moneyputput"></a><a name="money_put__put"></a>  money_put::PUT  
 Преобразует число или строку в последовательность символов, представляющую денежное значение.  
  
```  
iter_type put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,   
    const string_type& val) const;

 
iter_type put(
    iter_type next,   
    bool _Intl,   
    ios_base& _Iosbase,  
    CharType _Fill,  
    long double val) const;
```  
  
### <a name="parameters"></a>Параметры  
 ` next`  
 Итератор, обращающийся к первому элементу вставленной строки.  
  
 `_Intl`  
 Логическое значение, указывающее тип символ валюты, ожидаемого в последовательности: **true** Если международные, **false** Если внутренние.  
  
 `_Iosbase`  
 Формат флаг, который при набор указывает, что символ валюты является необязательным. в противном случае — является обязательным  
  
 `_Fill`  
 Символ, используемый для интервала.  
  
 ` val`  
 Строковый объект для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор вывода полученных адресов на позицию после последнего элемента.  
  
### <a name="remarks"></a>Примечания  
 Обе функции-члены возвращают [do_put](#money_put__do_put)( ` next`, `_Intl`, `_Iosbase`, `_Fill`, ` val`).  
  
### <a name="example"></a>Пример  
  
```  
// money_put_put.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
//   locale loc( "german_germany" );  
   locale loc( "english_canada" );  
   basic_stringstream<char> psz, psz2;  
   ios_base::iostate st = 0;  
  
   psz2.imbue( loc );  
   psz2.flags( psz2.flags( )|ios_base::showbase ); // force the printing of the currency symbol  
   use_facet < money_put < char > >(loc).put(basic_ostream<char>::_Iter( psz2.rdbuf( ) ), true, psz2, st, 100012);  
   if (st & ios_base::failbit)  
      cout << "money_put( ) FAILED" << endl;  
   else  
      cout << "money_put( ) = \"" << psz2.rdbuf( )->str( ) <<"\""<< endl;     
  
   st = 0;  
};  
```  
  
```Output  
money_put( ) = "CAD1,000.12"  
```  
  
##  <a name="a-namemoneyputstringtypea-moneyputstringtype"></a><a name="money_put__string_type"></a>  money_put::STRING_TYPE  
 Тип, который описывает строка, содержащая символы типа **CharType**.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип, описывающий специализацию класса шаблона [basic_string](../standard-library/basic-string-class.md) объекты которых могут хранить последовательностей элементов из исходной последовательности.  
  
## <a name="see-also"></a>См. также раздел  
 [\< языкового стандарта>](../standard-library/locale.md)   
 [Класс Facet](../standard-library/locale-class.md#facet_class)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

