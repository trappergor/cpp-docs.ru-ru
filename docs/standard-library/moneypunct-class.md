---
title: "Класс moneypunct | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- moneypunct
- std.moneypunct
- xlocmon/std::moneypunct
- std::moneypunct
dev_langs:
- C++
helpviewer_keywords:
- moneypunct class
ms.assetid: cf2650da-3e6f-491c-95d5-23e57f582ee6
caps.latest.revision: 20
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 5bf4f8f69073e6c445f416a24b00e19b4a20adc4
ms.lasthandoff: 02/24/2017

---
# <a name="moneypunct-class"></a>Класс moneypunct
Класс шаблона, описывающий объект, который можно использовать в качестве аспекта языкового стандарта для описания последовательностей типа `CharType`, используемых для представления полей для ввода или вывода денежных значений. Если параметр шаблона `Intl` имеет значение `true`, соблюдаются международные конвенции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class CharType, bool Intl>  
class moneypunct;  
```  
  
#### <a name="parameters"></a>Параметры  
 `CharType`  
 Тип, используемый внутри программы для кодирования символов.  
  
 `Intl`  
 Флаг, указывающий, должны ли соблюдаться международные конвенции.  
  
## <a name="remarks"></a>Примечания  
 Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **id.**  
  
 Статический объект const intl хранит значение параметра-шаблона **Intl**.  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[moneypunct](#moneypunct__moneypunct)|Конструктор объектов типа `moneypunct`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#moneypunct__char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|  
|[string_type](#moneypunct__string_type)|Тип, описывающий строку, содержащую символы типа `CharType`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[curr_symbol](#moneypunct__curr_symbol)|Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа валюты.|  
|[decimal_point](#moneypunct__decimal_point)|Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.|  
|[do_curr_symbol](#moneypunct__do_curr_symbol)|Защищенная виртуальная функция-член, которая возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа валюты.|  
|[do_decimal_point](#moneypunct__do_decimal_point)|Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.|  
|[do_frac_digits](#moneypunct__do_frac_digits)|Защищенная виртуальная функция-член возвращает определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.|  
|[do_grouping](#moneypunct__do_grouping)|Защищенная виртуальная функция-член возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.|  
|[do_neg_format](#moneypunct__do_neg_format)|Защищенная виртуальная функция-член вызывается для возвращения определенного языковым стандартом правила форматирования выходных значений, содержащих отрицательные числа.|  
|[do_negative_sign](#moneypunct__do_negative_sign)|Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить последовательность элементов определенного языкового стандарта для использования в качестве символа знака отрицательного числа.|  
|[do_pos_format](#moneypunct__do_pos_format)|Защищенная виртуальная функция-член вызывается для возвращения определенного языковым стандартом правила форматирования выходных значений, содержащих положительные числа.|  
|[do_positive_sign](#moneypunct__do_positive_sign)|Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить последовательность элементов определенного языкового стандарта для использования в качестве символа знака положительного числа.|  
|[do_thousands_sep](#moneypunct__do_thousands_sep)|Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить последовательность элементов определенного языкового стандарта для использования в качестве символа разделителя тысяч.|  
|[frac_digits](#moneypunct__frac_digits)|Возвращает определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.|  
|[grouping](#moneypunct__grouping)|Возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.|  
|[neg_format](#moneypunct__neg_format)|Возвращает определенное языковым стандартом правило форматирования выходных значений с отрицательными числами.|  
|[negative_sign](#moneypunct__negative_sign)|Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа отрицательного числа.|  
|[pos_format](#moneypunct__pos_format)|Возвращает определенное языковым стандартом правило форматирования выходных значений с положительными числами.|  
|[positive_sign](#moneypunct__positive_sign)|Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа положительного числа.|  
|[thousands_sep](#moneypunct__thousands_sep)|Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа разделителя тысяч.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
##  <a name="a-namemoneypunctchartypea--moneypunctchartype"></a><a name="moneypunct__char_type"></a>  moneypunct::char_type  
 Тип, используемый для описания символа, используемого языковым стандартом.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом для параметра-шаблона **Chartype**.  
  
##  <a name="a-namemoneypunctcurrsymbola--moneypunctcurrsymbol"></a><a name="moneypunct__curr_symbol"></a>  moneypunct::curr_symbol  
 Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа валюты.  
  
```  
string_type curr_symbol() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая символ валюты.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_curr_symbol](#moneypunct__do_curr_symbol).  
  
### <a name="example"></a>Пример  
  
```cpp  
// moneypunct_curr_symbol.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct < char, true > &mpunct = use_facet < moneypunct < char, true > >(loc);  
   cout << loc.name( ) << " international currency symbol "<<  mpunct.curr_symbol( ) << endl;  
  
   const moneypunct < char, false> &mpunct2 = use_facet < moneypunct < char, false> >(loc);  
   cout << loc.name( ) << " domestic currency symbol "<<  mpunct2.curr_symbol( ) << endl;  
};  
```  
  
##  <a name="a-namemoneypunctdecimalpointa--moneypunctdecimalpoint"></a><a name="moneypunct__decimal_point"></a>  moneypunct::decimal_point  
 Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.  
  
```  
CharType decimal_point() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_decimal_point](#moneypunct__do_decimal_point).  
  
### <a name="example"></a>Пример  
  
```cpp  
// moneypunct_decimal_pt.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc("german_germany");  
  
   const moneypunct < char, true > &mpunct = use_facet   
      < moneypunct < char, true > >(loc);  
   cout << loc.name( ) << " international decimal point "  
        << mpunct.decimal_point( ) << endl;  
  
   const moneypunct < char, false> &mpunct2 = use_facet   
      < moneypunct < char, false> >(loc);  
   cout << loc.name( ) << " domestic decimal point "  
        << mpunct2.decimal_point( ) << endl;  
}  
```  
  
```Output  
German_Germany.1252 international decimal point ,  
German_Germany.1252 domestic decimal point ,  
```  
  
##  <a name="a-namemoneypunctdocurrsymbola--moneypunctdocurrsymbol"></a><a name="moneypunct__do_curr_symbol"></a>  moneypunct::do_curr_symbol  
 Защищенная виртуальная функция-член, которая возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа валюты.  
  
```  
virtual string_type do_curr_symbol() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.  
  
### <a name="example"></a>Пример  
  См. пример для [curr_symbol](#moneypunct__curr_symbol), где виртуальная функция-член вызывается из `curr_symbol`.  
  
##  <a name="a-namemoneypunctdodecimalpointa--moneypunctdodecimalpoint"></a><a name="moneypunct__do_decimal_point"></a>  moneypunct::do_decimal_point  
 Защищенная виртуальная функция-член, которая возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.  
  
```  
virtual CharType do_decimal_point() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Последовательность элементов определенного языкового стандарта для использования в качестве символа десятичного разделителя.  
  
### <a name="example"></a>Пример  
  См. пример для [decimal_point](#moneypunct__decimal_point), где виртуальная функция-член вызывается из `decimal_point`.  
  
##  <a name="a-namemoneypunctdofracdigitsa--moneypunctdofracdigits"></a><a name="moneypunct__do_frac_digits"></a>  moneypunct::do_frac_digits  
 Защищенная виртуальная функция-член, которая возвращает определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.  
  
```  
virtual int do_frac_digits() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.  
  
### <a name="example"></a>Пример  
  См. пример для [frac_digits](#moneypunct__frac_digits), где виртуальная функция-член вызывается из `frac_digits`.  
  
##  <a name="a-namemoneypunctdogroupinga--moneypunctdogrouping"></a><a name="moneypunct__do_grouping"></a>  moneypunct::do_grouping  
 Защищенная виртуальная функция-член, которая возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.  
  
```  
virtual string do_grouping() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.  
  
### <a name="example"></a>Пример  
  См. пример для [grouping](#moneypunct__grouping), где виртуальная функция-член вызывается из **grouping**.  
  
##  <a name="a-namemoneypunctdonegformata--moneypunctdonegformat"></a><a name="moneypunct__do_neg_format"></a>  moneypunct::do_neg_format  
 Защищенная виртуальная функция-член вызывается для возвращения определенного языковым стандартом правила форматирования выходных значений, содержащих отрицательные числа.  
  
```  
virtual pattern do_neg_format() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Защищенная виртуальная функция-член возвращает определенное языковым стандартом правило формирования денежного поля вывода для отрицательного значения. Каждый из четырех элементов **pattern::field** может принимать значения:  
  
- **none** для соответствия нулю или более пробелам или для формирования пустого значения.  
  
- **sign** для соответствия или формирования знака плюс или минус.  
  
- **space** для соответствия нулю или более пробелам или для формирования пробела.  
  
- **symbol** для соответствия или формирования символа валюты.  
  
- **value** для соответствия или формирования денежного значения.  
  
 Компоненты денежных полей вывода создаются, а компоненты денежных полей ввода сопоставляются в том порядке, в котором эти элементы появляются в **pattern::field**. Каждое из значений **sign**, **symbol**, **value**, а также **none** либо **space** должно встречаться ровно один раз. Значение **none** не должно быть первым. Значение space **не должно** быть первым или последним. Если **Intl** имеет значение true, то порядок — **symbol**, **sign**, **none**, затем **value**.  
  
 Версия-шаблон `moneypunct`\< **CharType**, **Intl**> возвращает `{`**money_base::symbol**, **money_base::sign**, **money_base::value**, **money_base::none**`}`.  
  
### <a name="example"></a>Пример  
  См. пример для [neg_format](#moneypunct__neg_format), где виртуальная функция-член вызывается из `neg_format`.  
  
##  <a name="a-namemoneypunctdonegativesigna--moneypunctdonegativesign"></a><a name="moneypunct__do_negative_sign"></a>  moneypunct::do_negative_sign  
 Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить последовательность элементов определенного языкового стандарта для использования в качестве символа знака отрицательного числа.  
  
```  
virtual string_type do_negative_sign() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Последовательность элементов определенного языкового стандарта для использования в качестве символа отрицательного числа.  
  
### <a name="example"></a>Пример  
  См. пример для [negative_sign](#moneypunct__negative_sign), где виртуальная функция-член вызывается из `negative_sign`.  
  
##  <a name="a-namemoneypunctdoposformata--moneypunctdoposformat"></a><a name="moneypunct__do_pos_format"></a>  moneypunct::do_pos_format  
 Защищенная виртуальная функция-член вызывается для возвращения определенного языковым стандартом правила форматирования выходных значений, содержащих положительные числа.  
  
```  
virtual pattern do_pos_format() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Защищенная виртуальная функция-член возвращает определенное языковым стандартом правило формирования денежного поля вывода для положительного значения. (Она также определяет способ сопоставления компонентов денежного поля ввода.) Кодирование такое же, как для [do_neg_format](#moneypunct__do_neg_format).  
  
 Версия-шаблон moneypunct\< **CharType**, **Inputlterator**> возвращает `{`**money_base::symbol**, **money_base::sign**, **money_base::value**, **money_base::none**`}`.  
  
### <a name="example"></a>Пример  
  См. пример для [pos_format](#moneypunct__pos_format), где виртуальная функция-член вызывается из `pos_format`.  
  
##  <a name="a-namemoneypunctdopositivesigna--moneypunctdopositivesign"></a><a name="moneypunct__do_positive_sign"></a>  moneypunct::do_positive_sign  
 Защищенная виртуальная функция-член, которая возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа положительного значения.  
  
```  
virtual string_type do_positive_sign() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Последовательность элементов определенного языкового стандарта для использования в качестве символа положительного значения.  
  
### <a name="example"></a>Пример  
  См. пример для [positive_sign](#moneypunct__positive_sign), где виртуальная функция-член вызывается из `positive_sign`.  
  
##  <a name="a-namemoneypunctdothousandssepa--moneypunctdothousandssep"></a><a name="moneypunct__do_thousands_sep"></a>  moneypunct::do_thousands_sep  
 Защищенная виртуальная функция-член, которая возвращает определенный языковым стандартом элемент для использования в качестве разделителя групп цифр слева от любого десятичного разделителя.  
  
```  
virtual CharType do_thousands_sep() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент определенного языкового стандарта для использования в качестве разделителя групп слева от любого десятичного разделителя.  
  
### <a name="example"></a>Пример  
  См. пример для [thousands_sep](#moneypunct__thousands_sep), где виртуальная функция-член вызывается из `thousands_sep`.  
  
##  <a name="a-namemoneypunctfracdigitsa--moneypunctfracdigits"></a><a name="moneypunct__frac_digits"></a>  moneypunct::frac_digits  
 Возвращает определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.  
  
```  
int frac_digits() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Определенное языковым стандартом количество цифр, которое будет отображаться справа от любого десятичного разделителя.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_frac_digits](#moneypunct__do_frac_digits).  
  
### <a name="example"></a>Пример  
  
```cpp  
// moneypunct_frac_digits.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
       use_facet <moneypunct <char, true> >(loc);  
   for (unsigned int i = 0; i <mpunct.grouping( ).length( ); i++ )  
   {  
      cout << loc.name( ) << " international grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(mpunct.grouping ( )[i])   
           << endl;  
   }  
   cout << loc.name( ) << " international frac_digits\n to the right"  
        << " of the radix character: "  
        << mpunct.frac_digits ( ) << endl << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
       use_facet <moneypunct <char, false> >(loc);  
   for (unsigned int i = 0; i <mpunct2.grouping( ).length( ); i++ )  
   {  
      cout << loc.name( ) << " domestic grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(mpunct2.grouping ( )[i])   
           << endl;  
   }  
   cout << loc.name( ) << " domestic frac_digits\n to the right"  
        << " of the radix character: "  
        << mpunct2.frac_digits ( ) << endl << endl;  
}  
```  
  
```Output  
German_Germany.1252 international grouping:  
 the 0th group to the left of the radix character is of size 3  
German_Germany.1252 international frac_digits  
 to the right of the radix character: 2  
  
German_Germany.1252 domestic grouping:  
 the 0th group to the left of the radix character is of size 3  
German_Germany.1252 domestic frac_digits  
 to the right of the radix character: 2  
```  
  
##  <a name="a-namemoneypunctgroupinga--moneypunctgrouping"></a><a name="moneypunct__grouping"></a>  moneypunct::grouping  
 Возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.  
  
```  
string grouping() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_grouping](#moneypunct__do_grouping).  
  
### <a name="example"></a>Пример  
  
```cpp  
// moneypunct_grouping.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
       use_facet <moneypunct <char, true> >( loc );  
   for (unsigned int i = 0; i <mpunct.grouping( ).length( ); i++ )  
   {  
      cout << loc.name( ) << " international grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(mpunct.grouping ( )[i])   
           << endl;  
   }  
   cout << loc.name( ) << " international frac_digits\n to the right"  
        << " of the radix character: "  
        << mpunct.frac_digits ( ) << endl << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
       use_facet <moneypunct <char, false> >( loc );  
   for (unsigned int i = 0; i <mpunct2.grouping( ).length( ); i++ )  
   {  
      cout << loc.name( ) << " domestic grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(mpunct2.grouping ( )[i])   
           << endl;  
   }  
   cout << loc.name( ) << " domestic frac_digits\n to the right"  
        << " of the radix character: "  
        << mpunct2.frac_digits ( ) << endl << endl;  
}  
```  
  
```Output  
German_Germany.1252 international grouping:  
 the 0th group to the left of the radix character is of size 3  
German_Germany.1252 international frac_digits  
 to the right of the radix character: 2  
  
German_Germany.1252 domestic grouping:  
 the 0th group to the left of the radix character is of size 3  
German_Germany.1252 domestic frac_digits  
 to the right of the radix character: 2  
```  
  
##  <a name="a-namemoneypunctmoneypuncta--moneypunctmoneypunct"></a><a name="moneypunct__moneypunct"></a>  moneypunct::moneypunct  
 Конструктор объектов типа `moneypunct`.  
  
```  
explicit moneypunct(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `_Refs`  
 Целочисленное значение, используемое для указания типа управления памятью для объекта.  
  
### <a name="remarks"></a>Примечания  
 Возможные значения параметра `_Refs` и их важность:  
  
-   0: время существования объекта управляется языковыми стандартами, которые его содержат.  
  
-   1: время существования объекта должно управляться вручную.  
  
-   \> 0: эти значения не определены.  
  
 Прямые примеры привести нельзя, так как деструктор защищен.  
  
 Конструктор инициализирует свой базовый объект с [locale::facet](../standard-library/locale-class.md#facet_class)(_ *Refs*).  
  
##  <a name="a-namemoneypunctnegformata--moneypunctnegformat"></a><a name="moneypunct__neg_format"></a>  moneypunct::neg_format  
 Возвращает определенное языковым стандартом правило форматирования выходных значений с отрицательными числами.  
  
```  
pattern neg_format() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Определенное языковым стандартом правило форматирования выходных значений с отрицательными числами.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_neg_format](#moneypunct__do_neg_format).  
  
### <a name="example"></a>Пример  
  
```cpp  
// moneypunct_neg_format.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main( ) {  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
      use_facet <moneypunct <char, true > >(loc);  
   cout << loc.name( ) << " international negative number format: "  
        << mpunct.neg_format( ).field[0]   
        << mpunct.neg_format( ).field[1]   
        << mpunct.neg_format( ).field[2]   
        << mpunct.neg_format( ).field[3] << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
      use_facet <moneypunct <char, false> >(loc);  
   cout << loc.name( ) << " domestic negative number format: "  
        << mpunct2.neg_format( ).field[0]   
        << mpunct2.neg_format( ).field[1]   
        << mpunct2.neg_format( ).field[2]   
        << mpunct2.neg_format( ).field[3] << endl;  
}  
```  
  
##  <a name="a-namemoneypunctnegativesigna--moneypunctnegativesign"></a><a name="moneypunct__negative_sign"></a>  moneypunct::negative_sign  
 Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа отрицательного числа.  
  
```  
string_type negative_sign() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа отрицательного числа.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_negative_sign](#moneypunct__do_negative_sign).  
  
### <a name="example"></a>Пример  
  
```cpp  
// moneypunct_neg_sign.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
      use_facet <moneypunct <char, true> >(loc);  
   cout << loc.name( ) << " international negative sign: "  
        << mpunct.negative_sign( ) << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
      use_facet <moneypunct <char, false> >(loc);  
   cout << loc.name( ) << " domestic negative sign: "  
        << mpunct2.negative_sign( ) << endl;  
  
   locale loc2( "French" );  
  
   const moneypunct <char, true> &mpunct3 =   
      use_facet <moneypunct <char, true> >(loc2);  
   cout << loc2.name( ) << " international negative sign: "  
        << mpunct3.negative_sign( ) << endl;  
  
   const moneypunct <char, false> &mpunct4 =   
      use_facet <moneypunct <char, false> >(loc2);  
   cout << loc2.name( ) << " domestic negative sign: "  
        << mpunct4.negative_sign( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 international negative sign: -  
German_Germany.1252 domestic negative sign: -  
French_France.1252 international negative sign: -  
French_France.1252 domestic negative sign: -  
```  
  
##  <a name="a-namemoneypunctposformata--moneypunctposformat"></a><a name="moneypunct__pos_format"></a>  moneypunct::pos_format  
 Возвращает определенное языковым стандартом правило форматирования выходных значений с положительными числами.  
  
```  
pattern pos_format() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Определенное языковым стандартом правило форматирования выходных значений с положительными числами.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_pos_format](#moneypunct__do_pos_format).  
  
### <a name="example"></a>Пример  
  
```cpp  
// moneypunct_pos_format.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main() {  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
      use_facet <moneypunct <char, true> >(loc);  
   cout << loc.name( ) << " international positive number format: "  
        << mpunct.pos_format( ).field[0]   
        << mpunct.pos_format( ).field[1]   
        << mpunct.pos_format( ).field[2]   
        << mpunct.pos_format( ).field[3] << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
      use_facet <moneypunct <char, false> >(loc);  
   cout << loc.name( ) << " domestic positive number format: "  
        << mpunct2.pos_format( ).field[0]   
        << mpunct2.pos_format( ).field[1]   
        << mpunct2.pos_format( ).field[2]   
        << mpunct2.pos_format( ).field[3] << endl;  
}  
```  
  
##  <a name="a-namemoneypunctpositivesigna--moneypunctpositivesign"></a><a name="moneypunct__positive_sign"></a>  moneypunct::positive_sign  
 Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа положительного числа.  
  
```  
string_type positive_sign() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Последовательность элементов определенного языкового стандарта для использования в качестве символа положительного числа.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_positive_sign](#moneypunct__do_positive_sign).  
  
### <a name="example"></a>Пример  
  
```cpp  
// moneypunct_pos_sign.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
  
using namespace std;  
  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
      use_facet <moneypunct <char, true > >(loc);  
   cout << loc.name( ) << " international positive sign:"  
        << mpunct.positive_sign( ) << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
      use_facet <moneypunct <char, false> >(loc);  
   cout << loc.name( ) << " domestic positive sign:"  
        << mpunct2.positive_sign( ) << endl;  
  
   locale loc2( "French" );  
  
   const moneypunct <char, true> &mpunct3 =   
      use_facet <moneypunct <char, true> >(loc2);  
   cout << loc2.name( ) << " international positive sign:"  
        << mpunct3.positive_sign( ) << endl;  
  
   const moneypunct <char, false> &mpunct4 =   
      use_facet <moneypunct <char, false> >(loc2);  
   cout << loc2.name( ) << " domestic positive sign:"  
        << mpunct4.positive_sign( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 international positive sign:  
German_Germany.1252 domestic positive sign:  
French_France.1252 international positive sign:  
French_France.1252 domestic positive sign:  
```  
  
##  <a name="a-namemoneypunctstringtypea--moneypunctstringtype"></a><a name="moneypunct__string_type"></a>  moneypunct::string_type  
 Тип, который описывает строку символов типа **CharType**.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [basic_string](../standard-library/basic-string-class.md), объекты которого могут хранить копии последовательности знаков препинания.  
  
##  <a name="a-namemoneypunctthousandssepa--moneypunctthousandssep"></a><a name="moneypunct__thousands_sep"></a>  moneypunct::thousands_sep  
 Возвращает последовательность элементов определенного языкового стандарта для использования в качестве символа разделителя тысяч.  
  
```  
CharType thousands_sep() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Последовательность элементов определенного языкового стандарта для использования в качестве символа разделителя тысяч.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_thousands_sep](#moneypunct__do_thousands_sep).  
  
### <a name="example"></a>Пример  
  
```cpp  
// moneypunct_thou_sep.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const moneypunct <char, true> &mpunct =   
       use_facet <moneypunct <char, true > >(loc);  
   cout << loc.name( ) << " international thousands separator: "  
        << mpunct.thousands_sep( ) << endl;  
  
   const moneypunct <char, false> &mpunct2 =   
      use_facet <moneypunct <char, false> >(loc);  
   cout << loc.name( ) << " domestic thousands separator: "  
        << mpunct2.thousands_sep( ) << endl << endl;  
  
   locale loc2( "english_canada" );  
  
   const moneypunct <char, true> &mpunct3 =   
       use_facet <moneypunct <char, true> >(loc2);  
   cout << loc2.name( ) << " international thousands separator: "  
        << mpunct3.thousands_sep( ) << endl;  
  
   const moneypunct <char, false> &mpunct4 =   
      use_facet <moneypunct <char, false> >(loc2);  
   cout << loc2.name( ) << " domestic thousands separator: "  
        << mpunct4.thousands_sep( ) << endl;  
}  
```  
  
```Output  
German_Germany.1252 international thousands separator: .  
German_Germany.1252 domestic thousands separator: .  
  
English_Canada.1252 international thousands separator: ,  
English_Canada.1252 domestic thousands separator: ,  
```  
  
## <a name="see-also"></a>См. также  
 [\<locale>](../standard-library/locale.md)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


