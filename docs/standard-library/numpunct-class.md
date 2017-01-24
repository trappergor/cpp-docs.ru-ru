---
title: "Класс numpunct | Microsoft Docs"
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
  - "xlocnum/std::numpunct"
  - "std::numpunct"
  - "numpunct"
  - "std.numpunct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numpunct - класс"
ms.assetid: 73fb93cc-ac11-4c98-987c-bfa6267df596
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс numpunct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс шаблона, описывающий объект, который может использоваться в качестве локального аспекта для описания последовательностей типа `CharType`, применяемых для представления информации о форматировании и пунктуации числовых и логических выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <class CharType>  
class numpunct : public locale::facet;  
```  
  
#### <a name="parameters"></a>Параметры  
 `CharType`  
 Тип, используемый внутри программы для кодирования символов в языковом стандарте.  
  
## <a name="remarks"></a>Примечания  
 Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **идентификатор.**  
  
### <a name="constructors"></a>Конструкторы  
  
|||  
|-|-|  
|[numpunct](#numpunct__numpunct)|Конструктор для объектов типа `numpunct`.|  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[char_type](#numpunct__char_type)|Тип, используемый для описания символа, используемого языковым стандартом.|  
|[STRING_TYPE](#numpunct__string_type)|Тип, описывающий строку, содержащую символы типа `CharType`.|  
  
### <a name="member-functions"></a>Функции-члены  
  
|||  
|-|-|  
|[decimal_point](#numpunct__decimal_point)|Возвращает элемент определенного языкового стандарта для использования в качестве десятичного разделителя.|  
|[do_decimal_point](#numpunct__do_decimal_point)|Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить элемент определенного языкового стандарта для использования в качестве десятичного разделителя.|  
|[do_falsename](#numpunct__do_falsename)|Защищенная виртуальная функция-член, вызываемая для возврата строки, которая будет использоваться как текстовое представление значения `false`.|  
|[do_grouping](#numpunct__do_grouping)|Защищенная виртуальная функция-член, вызываемая для того, чтобы возвратить определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.|  
|[do_thousands_sep](#numpunct__do_thousands_sep)|Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить элемент определенного языкового стандарта для использования в качестве разделителя тысяч.|  
|[do_truename](#numpunct__do_truename)|Защищенная виртуальная функция-член, вызываемая для возврата строки, которая будет использоваться как текстовое представление значения `true`.|  
|[falsename](#numpunct__falsename)|Возвращает строку, которая будет использоваться как текстовое представление значения `false`.|  
|[группирование](#numpunct__grouping)|Возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.|  
|[thousands_sep](#numpunct__thousands_sep)|Возвращает элемент определенного языкового стандарта для использования в качестве разделителя тысяч.|  
|[truename](#numpunct__truename)|Возвращает строку, которая будет использоваться как текстовое представление значения `true`.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \< языкового стандарта>  
  
 **Пространство имен:** std  
  
##  <a name="a-namenumpunctchartypea-numpunctchartype"></a><a name="numpunct__char_type"></a>  numpunct::char_type  
 Тип, используемый для описания символа, используемого языковым стандартом.  
  
```  
typedef CharType char_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является синонимом параметра шаблона **CharType.**  
  
##  <a name="a-namenumpunctdecimalpointa-numpunctdecimalpoint"></a><a name="numpunct__decimal_point"></a>  numpunct::decimal_point  
 Возвращает элемент определенного языкового стандарта для использования в качестве десятичного разделителя.  
  
```  
CharType decimal_point() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент определенного языкового стандарта для использования в качестве десятичного разделителя.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_decimal_point](#numpunct__do_decimal_point).  
  
### <a name="example"></a>Пример  
  
```  
// numpunct_decimal_point.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet <numpunct <char> >( loc);  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="a-namenumpunctdodecimalpointa-numpunctdodecimalpoint"></a><a name="numpunct__do_decimal_point"></a>  numpunct::do_decimal_point  
 Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить элемент определенного языкового стандарта для использования в качестве десятичного разделителя.  
  
```  
virtual CharType do_decimal_point() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент определенного языкового стандарта для использования в качестве десятичного разделителя.  
  
### <a name="example"></a>Пример  
  В примере показано [decimal_point](#numpunct__decimal_point), где виртуальная функция-член вызывается `decimal_point`.  
  
##  <a name="a-namenumpunctdofalsenamea-numpunctdofalsename"></a><a name="numpunct__do_falsename"></a>  numpunct::do_falsename  
 Защищенные виртуальная функция-член возвращает последовательность для использования в качестве текстовое представление значения **false**.  
  
```  
virtual string_type do_falsename() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая последовательности для использования как текстовое представление значения **false**.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает строку «false» для представления значения **false** во всех языковых стандартах.  
  
### <a name="example"></a>Пример  
  В примере показано [falsename](#numpunct__falsename), где виртуальная функция-член вызывается `falsename`.  
  
##  <a name="a-namenumpunctdogroupinga-numpunctdogrouping"></a><a name="numpunct__do_grouping"></a>  numpunct::do_grouping  
 Защищенная виртуальная функция-член, вызываемая для того, чтобы возвратить определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.  
  
```  
virtual string do_grouping() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Языковым стандартом правило группирования цифр слева от любого десятичного разделителя.  
  
### <a name="remarks"></a>Примечания  
 Защищенная виртуальная функция-член возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя. Кодирование — так же, как **lconv::grouping**.  
  
### <a name="example"></a>Пример  
  В примере показано [группирование](#numpunct__grouping), где виртуальная функция-член вызывается **группирование**.  
  
##  <a name="a-namenumpunctdothousandssepa-numpunctdothousandssep"></a><a name="numpunct__do_thousands_sep"></a>  numpunct::do_thousands_sep  
 Защищенная виртуальная функция-член, которая вызывается, чтобы возвратить элемент определенного языкового стандарта для использования в качестве разделителя тысяч.  
  
```  
virtual CharType do_thousands_sep() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает элемент определенного языкового стандарта для использования в качестве разделителя тысяч.  
  
### <a name="remarks"></a>Примечания  
 Защищенные виртуальная функция-член возвращает элемент определенного языкового стандарта типа **CharType** для использования в качестве разделителя групп слева от любого десятичного разделителя.  
  
### <a name="example"></a>Пример  
  В примере показано [thousands_sep](#numpunct__thousands_sep), где виртуальная функция-член вызывается `thousands_sep`.  
  
##  <a name="a-namenumpunctdotruenamea-numpunctdotruename"></a><a name="numpunct__do_truename"></a>  numpunct::do_truename  
 Защищенная виртуальная функция-член, вызываемая для возврата строки, используемой как текстовое представление значения **true**.  
  
```  
virtual string_type do_truename() const;
```  
  
### <a name="remarks"></a>Примечания  
 Строка, используемая как текстовое представление значения **true**.  
  
 Все языковые стандарты возвращают строку «true» для представления значения **true**.  
  
### <a name="example"></a>Пример  
  В примере показано [truename](#numpunct__truename), где виртуальная функция-член вызывается `truename`.  
  
##  <a name="a-namenumpunctfalsenamea-numpunctfalsename"></a><a name="numpunct__falsename"></a>  numpunct::falsename  
 Возвращает строку для использования в качестве текстовое представление значения **false**.  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка, содержащая последовательность **CharType**для использования как текстовое представление значения **false**.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает строку «false» для представления значения **false** во всех языковых стандартах.  
  
 Функция-член возвращает [do_falsename](#numpunct__do_falsename).  
  
### <a name="example"></a>Пример  
  
```  
// numpunct_falsename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct <char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2( "French" );  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >(loc2);  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
##  <a name="a-namenumpunctgroupinga-numpunctgrouping"></a><a name="numpunct__grouping"></a>  numpunct::GROUPING  
 Возвращает определенное языковым стандартом правило группирования цифр слева от любого десятичного разделителя.  
  
```  
string grouping() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Языковым стандартом правило группирования цифр слева от любого десятичного разделителя.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_grouping](#numpunct__do_grouping).  
  
### <a name="example"></a>Пример  
  
```  
// numpunct_grouping.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany");  
  
   const numpunct <char> &npunct =   
       use_facet < numpunct <char> >( loc );  
   for (unsigned int i = 0; i < npunct.grouping( ).length( ); i++)  
   {  
      cout << loc.name( ) << " international grouping:\n the "  
           << i <<"th group to the left of the radix character "  
           << "is of size " << (int)(npunct.grouping ( )[i])   
           << endl;  
   }  
}  
```  
  
```Output  
German_Germany.1252 international grouping:  
 the 0th group to the left of the radix character is of size 3  
```  
  
##  <a name="a-namenumpunctnumpuncta-numpunctnumpunct"></a><a name="numpunct__numpunct"></a>  numpunct::numpunct  
 Конструктор для объектов типа `numpunct`.  
  
```  
explicit numpunct(size_t _Refs = 0);
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
  
##  <a name="a-namenumpunctstringtypea-numpunctstringtype"></a><a name="numpunct__string_type"></a>  numpunct::STRING_TYPE  
 Тип, который описывает строка, содержащая символы типа **CharType**.  
  
```  
typedef basic_string<CharType, Traits, Allocator> string_type;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип, описывающий специализацию класса шаблона [basic_string](../standard-library/basic-string-class.md) объекты которых могут хранить копии последовательности знаков препинания.  
  
##  <a name="a-namenumpunctthousandssepa-numpunctthousandssep"></a><a name="numpunct__thousands_sep"></a>  numpunct::thousands_sep  
 Возвращает элемент определенного языкового стандарта для использования в качестве разделителя тысяч.  
  
```  
CharType thousands_sep() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент определенного языкового стандарта для использования в качестве тысяч разделителя.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_thousands_sep](#numpunct__do_thousands_sep).  
  
### <a name="example"></a>Пример  
  
```  
// numpunct_thou_sep.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "german_germany" );  
  
   const numpunct <char> &npunct =   
   use_facet < numpunct < char > >( loc );  
   cout << loc.name( ) << " decimal point "<<   
   npunct.decimal_point( ) << endl;  
   cout << loc.name( ) << " thousands separator "   
   << npunct.thousands_sep( ) << endl;  
};  
```  
  
```Output  
German_Germany.1252 decimal point ,  
German_Germany.1252 thousands separator .  
```  
  
##  <a name="a-namenumpuncttruenamea-numpuncttruename"></a><a name="numpunct__truename"></a>  numpunct::truename  
 Возвращает строку для использования в качестве текстовое представление значения **true**.  
  
```  
string_type falsename() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Строка, используемая как текстовое представление значения **true**.  
  
### <a name="remarks"></a>Примечания  
 Функция-член возвращает [do_truename](#numpunct__do_truename).  
  
 Все языковые стандарты возвращают строку «true» для представления значения **true**.  
  
### <a name="example"></a>Пример  
  
```  
// numpunct_truename.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
#include <sstream>  
using namespace std;  
int main( )  
{  
   locale loc( "English" );  
  
   const numpunct < char> &npunct = use_facet <numpunct <char> >( loc );  
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;  
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;  
  
   locale loc2("French");  
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >( loc2 );  
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;  
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;  
}  
```  
  
```Output  
English_United States.1252 truename true  
English_United States.1252 falsename false  
French_France.1252 truename true  
French_France.1252 falsename false  
```  
  
## <a name="see-also"></a>См. также раздел  
 [\< языкового стандарта>](../standard-library/locale.md)   
 [Класс Facet](../standard-library/locale-class.md#facet_class)   
 [Потокобезопасность в стандартной библиотеке C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

