---
title: "Класс money_put | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xlocmon/std::money_put
- xlocmon/std::money_put::char_type
- xlocmon/std::money_put::iter_type
- xlocmon/std::money_put::string_type
- xlocmon/std::money_put::do_put
- xlocmon/std::money_put::put
dev_langs:
- C++
helpviewer_keywords:
- std::money_put [C++]
- std::money_put [C++], char_type
- std::money_put [C++], iter_type
- std::money_put [C++], string_type
- std::money_put [C++], do_put
- std::money_put [C++], put
ms.assetid: f439fd56-c9b1-414c-95e1-66c918c6eee6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 33554a3c3422a06693a7daee60c1ccaa47bd00c7
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="moneyput-class"></a>Класс money_put
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
 Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **id.**  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[money_put](#money_put)|Конструктор для объектов типа `money_put`.|  
  
### <a name="typedefs"></a>Определения типов  
  
|||  
|-|-|  
|[char_type](#char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|  
|[iter_type](#iter_type)|Тип, который описывает итератор вывода.|  
|[string_type](#string_type)|Тип, описывающий строку, содержащую символы типа `CharType`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[do_put](#do_put)|Виртуальная функция, вызываемая для преобразования числа или строки в последовательность символов, представляющую денежное значение.|  
|[put](#put)|Преобразует число или строку в последовательность символов, представляющую денежное значение.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<locale>  
  
 **Пространство имен:** std  
  
##  <a name="char_type"></a>  money_put::char_type  
 Тип, используемый для описания символа, используемого языковым стандартом.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом для параметра-шаблона **CharType**.  
  
##  <a name="do_put"></a>  money_put::do_put  
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
 `next`  
 Итератор, адресующий первый элемент во вставляемой строке.  
  
 `_Intl`  
 Логическое значение, указывающее тип символа валюты, ожидаемого в последовательности: **true** для международного символа, **false** для внутреннего.  
  
 `_Iosbase`  
 Флаг формата, который при установке указывает, что символ валюты является необязательным. В противном случае он обязателен.  
  
 `_Fill`  
 Символ, используемый для пробелов.  
  
 `val`  
 Строковый объект для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор вывода, который адресует позицию после последнего сформированного элемента.  
  
### <a name="remarks"></a>Примечания  
 Первая виртуальная защищенная функция-член создает последовательные элементы, начиная с `next` для создания выходного денежного поля из объекта [string_type](#string_type) `val`. Последовательности, контролируемой `val` должно начинаться с одного или нескольких десятичных цифр, при необходимости предшествует знак минуса (-), который представляет объем. Функция возвращает итератор, обозначающий первый элемент за пределами созданного выходного денежного поля.  
  
 Вторая защищенная виртуальная функция-член ведет себя так же, как и первая, за исключением того, что она фактически сначала преобразует `val` в последовательность десятичных цифр, при необходимости начинающуюся со знака минус, затем преобразует эту последовательность, как описано выше.  
  
 Формат выходного поля денежных значений определяется [аспектом языкового стандарта](../standard-library/locale-class.md#facet_class) fac, возвращаемого эффективным вызовом [use_facet](../standard-library/locale-functions.md#use_facet) < [moneypunct](../standard-library/moneypunct-class.md)\< **CharType**, **intl**> >(**iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)).  
  
 В частности:  
  
- **fac**. [pos_format](../standard-library/moneypunct-class.md#pos_format) определяет порядок, в котором компоненты поля создаются для неотрицательного значения.  
  
- **fac**. [neg_format](../standard-library/moneypunct-class.md#neg_format) определяет порядок, в котором компоненты поля создаются для отрицательного значения.  
  
- **fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol) определяет последовательность элементов для создания символа валюты.  
  
- **fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign) определяет последовательность элементов для создания положительного знака.  
  
- **fac**. [positive_sign](../standard-library/moneypunct-class.md#negative_sign) определяет последовательность элементов для создания отрицательного знака.  
  
- **fac**. [grouping](../standard-library/moneypunct-class.md#grouping) определяет, как группируются цифры слева от любого десятичного разделителя.  
  
- **fac**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep) определяет элемент, разделяющий группы цифр слева от любого десятичного разделителя.  
  
- **fac**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point) определяет элемент, который отделяет целочисленное значение от любых цифр дробного значения.  
  
- **fac**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits) определяет количество значимых цифр справа от любого десятичного разделителя.  
  
 Если строка знака (**fac**. `negative_sign` или **fac**. `positive_sign`) имеет более одного элемента, только первый элемент создается, если элемент, равный **money_base::sign**, отображается в шаблоне формата (**fac**. `neg_format` или **fac**. `pos_format`). Все оставшиеся элементы создаются в конце поля вывода денежных значений.  
  
 Если **iosbase**. [flags](../standard-library/ios-base-class.md#flags) & [showbase](../standard-library/ios-functions.md#showbase) не равно нулю, то строка **fac**. `curr_symbol`создается, когда в шаблоне формата появляется элемент, равный **money_base::symbol**. В противном символ валюты не создается.  
  
 Если не накладываются ограничения по группированию со стороны **fac**. **grouping** (первый элемент имеет значение CHAR_MAX), то никакие экземпляры **fac**. `thousands_sep` не создаются в разделе значения денежных полей (если в шаблоне формата появляется элемент, равный **money_base::value**). Если **fac**. `frac_digits` — нуль, то после десятичных цифр не создаются никакие экземпляры **fac**. `decimal_point`. В противном случае результат поля вывода денежных значений будет иметь младшие десятичные цифры **fac**. `frac_digits` справа от десятичного разделителя.  
  
 Заполнение происходит как для любого числового поля вывода, за исключением того, что, если значение **iosbase**. **flags** & **iosbase**. [internal](../standard-library/ios-functions.md#internal) не нулевое, любое внутреннее заполнение создается там, где в шаблоне формата появляется элемент, равный **money_base::space**, если он есть. В противном случае внутреннее заполнение предшествует создаваемой последовательности. Символ заполнения — **fill**.  
  
 Функция вызывает **iosbase**. **width**(0) для сброса ширины поля в нуль.  
  
### <a name="example"></a>Пример  
  См. пример для [put](#put), где виртуальная функция-член вызывается из **put**.  
  
##  <a name="iter_type"></a>  money_put::iter_type  
 Тип, который описывает итератор вывода.  
  
```  
typedef OutputIterator iter_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра-шаблона **OutputIterator.**  
  
##  <a name="money_put"></a>  money_put::money_put  
 Конструктор для объектов типа `money_put`.  
  
```  
explicit money_put(size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `_Refs`  
 Целочисленное значение, используемое для указания типа управления памятью для объекта.  
  
### <a name="remarks"></a>Примечания  
 Возможные значения параметра `_Refs` и их важность:  
  
-   0: время существования объекта управляется языковыми стандартами, которые его содержат.  
  
-   1: время существования объекта должно управляться вручную.  
  
-   \> 1: эти значения не определены.  
  
 Прямые примеры привести нельзя, так как деструктор защищен.  
  
 Конструктор инициализирует свой базовый объект с **locale::**[facet](../standard-library/locale-class.md#facet_class)(`_Refs`).  
  
##  <a name="put"></a>  money_put::put  
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
 `next`  
 Итератор, адресующий первый элемент во вставляемой строке.  
  
 `_Intl`  
 Логическое значение, указывающее тип символа валюты, ожидаемого в последовательности: **true** для международного символа, **false** для внутреннего.  
  
 `_Iosbase`  
 Флаг формата, который при установке указывает, что символ валюты является необязательным. В противном случае он обязателен.  
  
 `_Fill`  
 Символ, используемый для пробелов.  
  
 `val`  
 Строковый объект для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Итератор вывода, который адресует позицию после последнего сформированного элемента.  
  
### <a name="remarks"></a>Примечания  
 Обе функции-члены возвращают [do_put](#do_put)(`next`, `_Intl`, `_Iosbase`, `_Fill`, `val`).  
  
### <a name="example"></a>Пример  
  
```cpp  
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
  
##  <a name="string_type"></a>  money_put::string_type  
 Тип, который описывает строку символов типа **CharType**.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [basic_string](../standard-library/basic-string-class.md), объекты которого могут хранить последовательности элементов из входной последовательности.  
  
## <a name="see-also"></a>См. также  
 [\<locale>](../standard-library/locale.md)   
 [Класс facet](../standard-library/locale-class.md#facet_class)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

