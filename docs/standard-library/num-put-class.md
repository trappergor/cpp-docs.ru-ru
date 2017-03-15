---
title: "Класс num_put | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::num_put"
  - "xlocnum/std::num_put"
  - "num_put"
  - "std.num_put"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "num_put - класс"
ms.assetid: 36c5bffc-8283-4201-8ed4-78c4d81f8a17
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# Класс num_put
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Шаблонный класс, описывающий объект, который можно использовать как аспект языкового стандарта для управления преобразованиями числовых значений в последовательности типа `CharType`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class CharType,  
    class OutputIterator = ostreambuf_iterator<CharType>>  
class num_put : public locale::facet;  
```  
  
#### <a name="parameters"></a>Параметры  
 `CharType`  
 Тип, используемый внутри программы для кодирования символов в языковом стандарте.  
  
 `OutputIterator`  
 Тип итератора, куда численные функции записывают свои выходные данные.  
  
## <a name="remarks"></a>Примечания  
 Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **идентификатор.**  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[num_put](#num_put__num_put)|Конструктор для объектов типа `num_put`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#num_put__char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|  
|[iter_type](#num_put__iter_type)|Тип, который описывает итератор вывода.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[do_put](#num_put__do_put)|Виртуальная функция, которая вызывается для преобразования числа в последовательность `CharType`, представляющую это число в формате для определенного языкового стандарта.|  
|[PUT](#num_put__put)|Преобразует число в последовательность `CharType`, представляющую число в формате для определенного языкового стандарта.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< языкового стандарта>  
  
 **Пространство имен:** std  
  
##  <a name="a-namenumputchartypea-numputchartype"></a><a name="num_put__char_type"></a>  num_put::char_type  
 Тип, используемый для описания символа, используемого языковым стандартом.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона **CharType**.  
  
##  <a name="a-namenumputdoputa-numputdoput"></a><a name="num_put__do_put"></a>  num_put::do_put  
 Виртуальная функция, вызываемая для преобразования числа в последовательность **CharType**представляющую число в формате для определенного языкового стандарта.  
  
```  
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    bool val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    unsigned long val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    double val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long double val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const void* val) const;

 
virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const long long val) const;

virtual iter_type do_put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const unsigned long long val) const;
```  
  
### <a name="parameters"></a>Параметры  
 ` next`  
 Итератор, обращающийся к первому элементу вставленной строки.  
  
 `_Iosbase`  
 Указанный поток, содержащий языкового стандарта с numpunct аспект, применяемый прерывая выходные данные и флаги для форматирования выходных данных.  
  
 `_Fill`  
 Символ, используемый для интервала.  
  
 ` val`  
 Числа или логического типа, должны быть выведены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор вывода полученных адресов на позицию после последнего элемента.  
  
### <a name="remarks"></a>Примечания  
 Первая функция защищенный виртуальный член создает последовательных элементов, начиная с ` next` для получения выходных данных целое поле из значения ` val`. Функция возвращает итератор, назначение Далее место для вставки элемента за пределами поле выходных данных генерируемое целое число.  
  
 Поле выходных данных integer создается с тем же правилам, используемых функций печати для создания ряда `char` элементы в файл. Каждый такой элемент char полагается на эквивалентные элементы типа **CharType** простое взаимно-однозначное сопоставление. Где печати функция заполняет поля с пробелами или цифры 0, тем не менее, `do_put` вместо использует **заполнения**. Спецификации преобразования эквивалентные печати определяется следующим образом:  
  
-   Если **iosbase**. [флаги](../standard-library/ios-base-class.md#ios_base__flags) & `ios_base::basefield` == `ios_base::`[oct](../Topic/%3Cios%3E%20functions.md#oct), спецификация преобразования **lo**.  
  
-   Если **iosbase.flags** & **ios_base::basefield** == `ios_base::`[шестнадцатеричное](../Topic/%3Cios%3E%20functions.md#hex), спецификация преобразования **lx**.  
  
-   В противном случае — спецификация преобразования является **ld**.  
  
 Если **iosbase**. [Ширина](../standard-library/ios-base-class.md#ios_base__width) имеет ненулевое значение, добавляется поле шириной этого значения. Затем вызывается функция **iosbase**. **Ширина**(0), чтобы ширина поля равным нулю.  
  
 Заполнение происходит только в том случае, если минимальное число элементов *N* необходимо указать поле выходных данных является менее **iosbase**. [Ширина](../standard-library/ios-base-class.md#ios_base__width). Такого заполнения состоит из последовательности *N* – **Ширина** копий **заполнения**. Затем заполнение выполняется следующим образом:  
  
-   Если **iosbase**. **флаги** & `ios_base::adjustfield` == `ios_base::`[левой](../Topic/%3Cios%3E%20functions.md#left), флаг **–** добавляется. (Заполнение выполняется после созданного текста).  
  
-   Если **iosbase.flags** & **ios_base::adjustfield** == `ios_base::`[внутренней](../Topic/%3Cios%3E%20functions.md#internal), флаг **0** добавляется. (Для вывода числовых полей, заполнение выполняется где функций печати рукописного ввода с 0).  
  
-   В противном случае — дополнительный флаг не добавляется. (Заполнение выполняется перед создаваемой последовательности).  
  
 Наконец:  
  
-   Если **iosbase**. **флаги** & `ios_base::`[showpos](../Topic/%3Cios%3E%20functions.md#showpos) не равно нулю, этот флаг **+** добавляются к спецификации преобразования.  
  
-   Если **iosbase**. **флаги** & **ios_base::**[showbase](../Topic/%3Cios%3E%20functions.md#showbase) не равно нулю, этот флаг **#** добавляются к спецификации преобразования.  
  
 Выходной формат целое поля определяется [аспекта языкового стандарта](../standard-library/locale-class.md#facet_class)**ОС** возвращаемый вызовом метода [use_facet](../Topic/%3Clocale%3E%20functions.md#use_facet) < [numpunct](../standard-library/numpunct-class.md)\< **Elem**> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#ios_base__getloc)). В частности:  
  
- **ОС**. [Группирование](../standard-library/numpunct-class.md#numpunct__grouping) определяет способ группировки цифр слева от любого десятичного разделителя  
  
- **ОС**. [thousands_sep](../standard-library/numpunct-class.md#numpunct__thousands_sep) определяет последовательность, разделяющую группы цифр слева от любого десятичного разделителя  
  
 Если накладываемые без ограничений группирования **ОС**. **Группирование** (первый элемент имеет значение CHAR_MAX), затем экземпляры **ОС**. `thousands_sep` создаются в поле выходных данных. В противном случае — после печати преобразование происходит вставляется разделитель.  
  
 Вторая функция защищенный виртуальный член:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    unsigned long val) const;
```  
  
 ведет себя так же как и первая, за исключением того, что он заменяет спецификации преобразования **ld** с **lu**.  
  
 Третья функция защищенный виртуальный член:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    double val) const;
```  
  
 ведет себя так же как и первая, за исключением того, что она создает поле выходные данные с плавающей запятой из значения **val**. **ОС**. [decimal_point](../standard-library/numpunct-class.md#numpunct__decimal_point) определяет последовательность, разделяющую целое число цифр после запятой. Спецификации преобразования эквивалентные печати определяется следующим образом:  
  
-   Если **iosbase**. **флаги** & `ios_base::floatfield` == `ios_base::`[фиксированной](../Topic/%3Cios%3E%20functions.md#fixed), спецификация преобразования **lf**.  
  
-   Если **iosbase**. **флаги** & **ios_base::floatfield** == `ios_base::`[научных](../Topic/%3Cios%3E%20functions.md#scientific), спецификации преобразования является `le`. Если **iosbase**. **флаги** & `ios_base::`[прописные](../Topic/%3Cios%3E%20functions.md#uppercase) не равно нулю, **e** заменяется **E**.  
  
-   В противном случае — спецификация преобразования является **lg**. Если **iosbase**. **флаги** & **ios_base::uppercase** не равно нулю, **g** заменяется **G**.  
  
 Если **iosbase**. **флаги** & **ios_base::fixed** отлично от нуля или если **iosbase**. [точность](../standard-library/ios-base-class.md#ios_base__precision) не равно нулю, точность со значением **iosbase**. **точность** добавляются к спецификации преобразования. Заполнение, ведет себя так же, как целое поле выходных данных. Символ заполнения **заполнения**. Наконец:  
  
-   Если **iosbase**. **флаги** & `ios_base::`[showpos](../Topic/%3Cios%3E%20functions.md#showpos) не равно нулю, этот флаг **+** добавляются к спецификации преобразования.  
  
-   Если **iosbase**. **флаги** & `ios_base::`[showpoint](../Topic/%3Cios%3E%20functions.md#showpoint) отлично от нуля, флаг **#** добавляются к спецификации преобразования.  
  
 Четвертый виртуальной защищенных функции-члена:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    long double val) const;
```  
  
 ведет себя так же третий, за исключением того, что квалификатор **l** в преобразовании заменяется спецификации **L**.  
  
 Пятый виртуальной защищенных функции-члена:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    const void* val) const;
```  
  
 работает так же, во-первых, за исключением того, что спецификация преобразования `p`**,** плюс любой квалификатор, необходимые для задания заполнения.  
  
 Шестой виртуальной защищенных функции-члена:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& _Iosbase,  
    CharType _Fill,
    bool val) const;
```  
  
 ведет себя так же как и первая, за исключением того, что он создает выходные данные логическое поле из ` val`.  
  
 Вывод логическое поле принимает одну из двух форм. Если **iosbase**. **флаги** & `ios_base::`[boolalpha](../Topic/%3Cios%3E%20functions.md#boolalpha) — **false**, функция-член возвращает `do_put`(_ *Далее*, \_ *Iosbase*, \_ *заполнения*, ( **много**) ` val`), создающего обычно созданной последовательности либо 0 (для **false**) или 1 (для **значение true,**). В противном случае — созданный последовательность является либо **ОС**. [falsename](../standard-library/numpunct-class.md#numpunct__falsename)`)` (для **false**), или **ОС**. [truename](../standard-library/numpunct-class.md#numpunct__truename) (для **значение true,**).  
  
 Седьмой виртуальной защищенных функции-члена:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,  
    Elem fill,
    long long val) const;
```  
  
 ведет себя так же как и первая, за исключением того, что он заменяет спецификации преобразования **ld** с **lld**.  
  
 Восьмой виртуальной защищенных функции-члена:  
  
```  
virtual iter_type do_put(iter_type next,
    ios_base& iosbase,  
    Elem fill,
    unsigned long long val) const;
```  
  
 ведет себя так же как и первая, за исключением того, что он заменяет спецификации преобразования `ld` с `llu`.  
  
### <a name="example"></a>Пример  
  В примере показано [поместить](#num_put__put), который вызывает метод `do_put`.  
  
##  <a name="a-namenumputitertypea-numputitertype"></a><a name="num_put__iter_type"></a>  num_put::iter_type  
 Тип, который описывает итератор вывода.  
  
```  
typedef OutputIterator iter_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона **OutputIterator.**  
  
##  <a name="a-namenumputnumputa-numputnumput"></a><a name="num_put__num_put"></a>  num_put::num_put  
 Конструктор для объектов типа `num_put`.  
  
```  
explicit num_put(size_t _Refs = 0);
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
  
 Конструктор инициализирует свой базовый объект с **locale::**[аспекта](../standard-library/locale-class.md#facet_class)(_ *Refs*).  
  
##  <a name="a-namenumputputa-numputput"></a><a name="num_put__put"></a>  num_put::PUT  
 Преобразует число в последовательность **CharType**представляющую число в формате для определенного языкового стандарта.  
  
```  
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    bool val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    unsigned long val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    Long long val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    Unsigned long long val) const;

 
 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    double val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    long double val) const;

 
iter_type put(
    iter_type dest,  
    ios_base& _Iosbase,  
    _Elem _Fill,  
    const void* val) const;
```  
  
### <a name="parameters"></a>Параметры  
 ` dest`  
 Итератор, обращающийся к первому элементу вставленной строки.  
  
 `_Iosbase`  
 Указанный поток, содержащий языкового стандарта с numpunct аспект, применяемый прерывая выходные данные и флаги для форматирования выходных данных.  
  
 `_Fill`  
 Символ, используемый для интервала.  
  
 ` val`  
 Числа или логического типа, должны быть выведены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор вывода полученных адресов на позицию после последнего элемента.  
  
### <a name="remarks"></a>Примечания  
 Все функции-члены возвращают [do_put](#num_put__do_put)( ` next`, `_Iosbase`, `_Fill`, ` val`).  
  
### <a name="example"></a>Пример  
  
```  
// num_put_put.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
   basic_stringstream<char> psz2;  
   ios_base::iostate st = 0;  
   long double fVal;  
   cout << "The thousands separator is: "   
        << use_facet < numpunct <char> >(loc).thousands_sep( )   
        << endl;  
  
   psz2.imbue( loc );  
   use_facet < num_put < char > >  
      ( loc ).put(basic_ostream<char>::_Iter(psz2.rdbuf( ) ),  
                    psz2, ' ', fVal=1000.67);  
  
   if ( st & ios_base::failbit )  
      cout << "num_put( ) FAILED" << endl;  
   else  
      cout << "num_put( ) = " << psz2.rdbuf( )->str( ) << endl;  
}  
```  
  
```Output  
The thousands separator is: .  
num_put( ) = 1.000,67  
```  
  
## <a name="see-also"></a>См. также  
 [\< языкового стандарта>](../standard-library/locale.md)   
 [Класс Facet](../standard-library/locale-class.md#facet_class)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

