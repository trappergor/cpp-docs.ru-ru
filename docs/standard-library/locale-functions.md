---
title: "Функции &lt;locale&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- locale/std::has_facet
- locale/std::isalnum
- locale/std::isalpha
- locale/std::iscntrl
- locale/std::isdigit
- locale/std::isgraph
- locale/std::islower
- locale/std::isprint
- locale/std::ispunct
- locale/std::isspace
- locale/std::isupper
- locale/std::isxdigit
- locale/std::tolower
- locale/std::toupper
- locale/std::use_facet
ms.assetid: b06c1ceb-33a7-48d3-8d4b-2714bbb27f14
caps.latest.revision: "15"
manager: ghogen
helpviewer_keywords:
- std::has_facet [C++]
- std::isalnum [C++]
- std::isalpha [C++]
- std::iscntrl [C++]
- std::isdigit [C++]
- std::isgraph [C++]
- std::islower [C++]
- std::isprint [C++]
- std::ispunct [C++]
- std::isspace [C++]
- std::isupper [C++]
- std::isxdigit [C++]
- std::tolower [C++]
- std::toupper [C++]
- std::use_facet [C++]
ms.openlocfilehash: 28274279da6422edf7e92e4aca9a6425cd21a9e8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ltlocalegt-functions"></a>Функции &lt;locale&gt;
||||  
|-|-|-|  
|[has_facet](#has_facet)|[isalnum](#isalnum)|[isalpha](#isalpha)|  
|[iscntrl](#iscntrl)|[isdigit](#isdigit)|[isgraph](#isgraph)|  
|[islower](#islower)|[isprint](#isprint)|[ispunct](#ispunct)|  
|[isspace](#isspace)|[isupper](#isupper)|[isxdigit](#isxdigit)|  
|[tolower](#tolower)|[toupper](#toupper)|[use_facet](#use_facet)|  
  
##  <a name="has_facet"></a>  has_facet  
 Тестирует наличие того или иного аспекта в указанном языковом стандарте.  
  
```  
template <class Facet>  
bool has_facet(const locale& Loc);
```  
  
### <a name="parameters"></a>Параметры  
 `Loc`  
 Языковой стандарт, проверяемый на наличие аспекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если языковой стандарт имеет проверяемый аспект; **false**, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон позволяет проверить, перечислены ли необязательные аспекты в языковом стандарте перед вызовом `use_facet`, чтобы избежать исключения, которое может быть создано, если они не существуют.  
  
### <a name="example"></a>Пример  
  
```cpp  
// locale_has_facet.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )  
{  
   locale loc ( "German_Germany" );  
   bool result = has_facet <ctype<char> > ( loc );  
   cout << result << endl;  
}  
```  
  
```Output  
1  
```  
  
##  <a name="isalnum"></a>  isalnum  
 Проверяет, является ли элемент языкового стандарта буквенным или цифровым символом.  
  
```  
template <class CharType>  
bool isalnum(CharType Ch, const locale& Loc)  
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Буквенно-цифровой элемент для проверки.  
  
 `Loc`  
 Языковой стандарт, содержащий буквенно-цифровой элемент для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если проверяемый элемент является буквенно-цифровым; **false**, если это не так.  
  
### <a name="example"></a>Пример  
  
```cpp  
// locale_isalnum.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   bool result1 = isalnum ( 'L', loc);  
   bool result2 = isalnum ( '@', loc);  
   bool result3 = isalnum ( '3', loc);  
  
   if ( result1 )  
      cout << "The character 'L' in the locale is "  
           << "alphanumeric." << endl;  
   else  
      cout << "The character 'L' in the locale is "  
           << " not alphanumeric." << endl;  
  
   if ( result2 )  
      cout << "The character '@' in the locale is "  
           << "alphanumeric." << endl;  
   else  
      cout << "The character '@' in the locale is "  
           << " not alphanumeric." << endl;  
  
   if ( result3 )  
      cout << "The character '3' in the locale is "  
           << "alphanumeric." << endl;  
   else  
      cout << "The character '3' in the locale is "  
           << " not alphanumeric." << endl;  
}  
```  
  
```Output  
The character 'L' in the locale is alphanumeric.  
The character '@' in the locale is  not alphanumeric.  
The character '3' in the locale is alphanumeric.  
```  
  
##  <a name="isalpha"></a>  isalpha  
 Проверяет, является ли элемент языкового стандарта буквенным символом.  
  
```  
template <class CharType>  
bool isalpha(CharType Ch, const locale& Loc)  
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Проверяемый элемент.  
  
 `Loc`  
 Языковой стандарт, содержащий буквенный элемент для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если проверяемый элемент является буквенным; **false**, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон возвращает [use_facet](../standard-library/locale-functions.md#use_facet)< [ctype](../standard-library/ctype-class.md)\< **CharType**> >(`Loc`). [is](../standard-library/ctype-class.md#is)(**ctype**\< **CharType**>:: **alpha**, `Ch`).  
  
### <a name="example"></a>Пример  
  
```cpp  
// locale_isalpha.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   bool result1 = isalpha ( 'L', loc);  
   bool result2 = isalpha ( '@', loc);  
   bool result3 = isalpha ( '3', loc);  
  
   if ( result1 )  
      cout << "The character 'L' in the locale is "  
           << "alphabetic." << endl;  
   else  
      cout << "The character 'L' in the locale is "  
           << " not alphabetic." << endl;  
  
   if ( result2 )  
      cout << "The character '@' in the locale is "  
           << "alphabetic." << endl;  
   else  
      cout << "The character '@' in the locale is "  
           << " not alphabetic." << endl;  
  
   if ( result3 )  
      cout << "The character '3' in the locale is "  
           << "alphabetic." << endl;  
   else  
      cout << "The character '3' in the locale is "  
           << " not alphabetic." << endl;  
}  
```  
  
##  <a name="iscntrl"></a>  iscntrl  
 Определяет, является ли элемент языкового стандарта управляющим символом.  
  
```  
template <class CharType>  
bool iscntrl(CharType Ch, const locale& Loc)  
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Проверяемый элемент.  
  
 `Loc`  
 Языковой стандарт, содержащий элемент для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если проверяемый элемент является управляющим символом; **false**, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон возвращает [use_facet](../standard-library/locale-functions.md#use_facet)< [ctype](../standard-library/ctype-class.md)\< **CharType**> >(`Loc`). [is](../standard-library/ctype-class.md#is)(**ctype**\< **CharType**>:: **cntrl**, `Ch`).  
  
### <a name="example"></a>Пример  
  
```cpp  
// locale_iscntrl.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   bool result1 = iscntrl ( 'L', loc );  
   bool result2 = iscntrl ( '\n', loc );  
   bool result3 = iscntrl ( '\t', loc );  
  
   if ( result1 )  
      cout << "The character 'L' in the locale is "  
           << "a control character." << endl;  
   else  
      cout << "The character 'L' in the locale is "  
           << " not a control character." << endl;  
  
   if ( result2 )  
      cout << "The character-set 'backslash-n' in the locale\n is "  
           << "a control character." << endl;  
   else  
      cout << "The character-set 'backslash-n' in the locale\n is "  
           << " not a control character." << endl;  
  
   if ( result3 )  
      cout << "The character-set 'backslash-t' in the locale\n is "  
           << "a control character." << endl;  
   else  
      cout << "The character-set 'backslash-n' in the locale \n is "  
           << " not a control character." << endl;  
}  
```  
  
##  <a name="isdigit"></a>  isdigit  
 Определяет, является ли элемент языкового стандарта цифровым символом.  
  
```  
template <class CharType>  
bool isdigit(CharType Ch, const locale& Loc)  
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Проверяемый элемент.  
  
 `Loc`  
 Языковой стандарт, содержащий элемент для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если проверяемый элемент является цифровым символом; **false**, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон возвращает [use_facet](../standard-library/locale-functions.md#use_facet)< [ctype](../standard-library/ctype-class.md)\< **CharType**> >(`Loc`). [is](../standard-library/ctype-class.md#is)(**ctype**\< **CharType**>:: **digit**, `Ch`).  
  
### <a name="example"></a>Пример  
  
```cpp  
// locale_is_digit.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   bool result1 = isdigit ( 'L', loc );  
   bool result2 = isdigit ( '@', loc );  
   bool result3 = isdigit ( '3', loc );  
  
   if ( result1 )  
      cout << "The character 'L' in the locale is "  
           << "a numeric character." << endl;  
   else  
      cout << "The character 'L' in the locale is "  
           << " not a numeric character." << endl;  
  
   if ( result2 )  
      cout << "The character '@' in the locale is "  
           << "a numeric character." << endl;  
   else  
      cout << "The character '@' in the locale is "  
           << " not a numeric character." << endl;  
  
   if ( result3 )  
      cout << "The character '3' in the locale is "  
           << "a numeric character." << endl;  
   else  
      cout << "The character '3' in the locale is "  
           << " not a numeric character." << endl;  
}  
```  
  
##  <a name="isgraph"></a>  isgraph  
 Проверяет, является ли элемент языкового стандарта буквенно-цифровым символом или символом пунктуации.  
  
```  
template <class CharType>  
bool isgraph(CharType Ch, const locale& Loc)  
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Проверяемый элемент.  
  
 `Loc`  
 Языковой стандарт, содержащий элемент для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если проверяемый элемент является знаком пунктуации; **false**, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон возвращает [use_facet](../standard-library/locale-functions.md#use_facet)< [ctype](../standard-library/ctype-class.md)\< **CharType**> >(`Loc`). [is](../standard-library/ctype-class.md#is)(**ctype**\< **CharType**>:: **graph**, `Ch`).  
  
### <a name="example"></a>Пример  
  
```cpp  
// locale_is_graph.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
  
using namespace std;  
  
int main( )  
{  
   locale loc ( "German_Germany" );  
   bool result1 = isgraph ( 'L', loc );  
   bool result2 = isgraph ( '\t', loc );  
   bool result3 = isgraph ( '.', loc );  
  
   if ( result1 )  
      cout << "The character 'L' in the locale is\n "  
           << "an alphanumeric or punctuation character." << endl;  
   else  
      cout << "The character 'L' in the locale is\n "  
           << " not an alphanumeric or punctuation character." << endl;  
  
   if ( result2 )  
      cout << "The character 'backslash-t' in the locale is\n "  
           << "an alphanumeric or punctuation character." << endl;  
   else  
      cout << "The character 'backslash-t' in the locale is\n "  
           << "not an alphanumeric or punctuation character." << endl;  
  
   if ( result3 )  
      cout << "The character '.' in the locale is\n "  
           << "an alphanumeric or punctuation character." << endl;  
   else  
      cout << "The character '.' in the locale is\n "  
           << " not an alphanumeric or punctuation character." << endl;  
}  
```  
  
##  <a name="islower"></a>  islower  
 Определяет, является ли элемент языкового стандарта символом в нижнем регистре.  
  
```  
template <class CharType>  
bool islower(CharType Ch, const locale& Loc)  
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Проверяемый элемент.  
  
 `Loc`  
 Языковой стандарт, содержащий элемент для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если проверяемый элемент является символом в нижнем регистре; **false**, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон возвращает [use_facet](../standard-library/locale-functions.md#use_facet)< [ctype](../standard-library/ctype-class.md)\< **CharType**> >(`Loc`). [is](../standard-library/ctype-class.md#is)(**ctype**\< **CharType**>:: **lower**, `Ch`).  
  
### <a name="example"></a>Пример  
  
```cpp  
// locale_islower.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   bool result1 = islower ( 'L', loc );  
   bool result2 = islower ( 'n', loc );  
   bool result3 = islower ( '3', loc );  
  
   if ( result1 )  
      cout << "The character 'L' in the locale is "  
           << "a lowercase character." << endl;  
   else  
      cout << "The character 'L' in the locale is "  
           << " not a lowercase character." << endl;  
  
   if ( result2 )  
      cout << "The character 'n' in the locale is "  
           << "a lowercase character." << endl;  
   else  
      cout << "The character 'n' in the locale is "  
           << " not a lowercase character." << endl;  
  
   if ( result3 )  
      cout << "The character '3' in the locale is "  
           << "a lowercase character." << endl;  
   else  
      cout << "The character '3' in the locale is "  
           << " not a lowercase character." << endl;  
}  
```  
  
##  <a name="isprint"></a>  isprint  
 Определяет, является ли элемент языкового стандарта символом, пригодным для печати.  
  
```  
template <class CharType>  
bool isprint(CharType Ch, const locale& Loc)  
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Проверяемый элемент.  
  
 `Loc`  
 Языковой стандарт, содержащий элемент для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если проверяемый элемент является печатным; **false**, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон возвращает [use_facet](../standard-library/locale-functions.md#use_facet)< [ctype](../standard-library/ctype-class.md)\< **CharType**> >(`Loc`). [is](../standard-library/ctype-class.md#is)(**ctype**\< **CharType**>:: **print**, `Ch`).  
  
### <a name="example"></a>Пример  
  
```cpp  
// locale_isprint.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
  
   bool result1 = isprint ( 'L', loc );  
   if ( result1 )  
      cout << "The character 'L' in the locale is "  
           << "a printable character." << endl;  
   else  
      cout << "The character 'L' in the locale is "  
           << " not a printable character." << endl;  
  
   bool result2 = isprint( '\t', loc );  
   if ( result2 )  
      cout << "The character 'backslash-t' in the locale is "  
           << "a printable character." << endl;  
   else  
      cout << "The character 'backslash-t' in the locale is "  
           << " not a printable character." << endl;  
  
   bool result3 = isprint( '\n', loc );  
   if ( result3 )  
      cout << "The character 'backslash-n' in the locale is "  
           << "a printable character." << endl;  
   else  
      cout << "The character 'backslash-n' in the locale is "  
           << " not a printable character." << endl;  
}  
```  
  
##  <a name="ispunct"></a>  ispunct  
 Определяет, является ли элемент языкового стандарта символом пунктуации.  
  
```  
template <class CharType>  
bool ispunct(CharType Ch, const locale& Loc)  
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Проверяемый элемент.  
  
 `Loc`  
 Языковой стандарт, содержащий элемент для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если проверяемый элемент является знаком пунктуации; **false**, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон возвращает [use_facet](../standard-library/locale-functions.md#use_facet)`<`[ctype](../standard-library/ctype-class.md)\< **CharType**> >(`Loc`). [is](../standard-library/ctype-class.md#is)(**ctype**\< **CharType**>:: **punct**, `Ch`).  
  
### <a name="example"></a>Пример  
  
```cpp  
// locale_ispunct.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   bool result1 = ispunct ( 'L', loc );  
   bool result2 = ispunct ( ';', loc );  
   bool result3 = ispunct ( '*', loc );  
  
   if ( result1 )  
      cout << "The character 'L' in the locale is "  
           << "a punctuation character." << endl;  
   else  
      cout << "The character 'L' in the locale is "  
           << " not a punctuation character." << endl;  
  
   if ( result2 )  
      cout << "The character ';' in the locale is "  
           << "a punctuation character." << endl;  
   else  
      cout << "The character ';' in the locale is "  
           << " not a punctuation character." << endl;  
  
   if ( result3 )  
      cout << "The character '*' in the locale is "  
           << "a punctuation character." << endl;  
   else  
      cout << "The character '*' in the locale is "  
           << " not a punctuation character." << endl;  
}  
```  
  
##  <a name="isspace"></a>  isspace  
 Определяет, является ли элемент языкового стандарта символом пустого пространства.  
  
```  
template <class CharType>  
bool isspace(CharType Ch, const locale& Loc)  
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Проверяемый элемент.  
  
 `Loc`  
 Языковой стандарт, содержащий элемент для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если проверяемый элемент является пробелом; **false**, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон возвращает [use_facet](../standard-library/locale-functions.md#use_facet)< [ctype](../standard-library/ctype-class.md)\< **CharType**> >(`Loc`). [is](../standard-library/ctype-class.md#is)(**ctype**\< **CharType**>:: **space**, `Ch`).  
  
### <a name="example"></a>Пример  
  
```cpp  
// locale_isspace.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   bool result1 = isspace ( 'L', loc );  
   bool result2 = isspace ( '\n', loc );  
   bool result3 = isspace ( ' ', loc );  
  
   if ( result1 )  
      cout << "The character 'L' in the locale is "  
           << "a whitespace character." << endl;  
   else  
      cout << "The character 'L' in the locale is "  
           << " not a whitespace character." << endl;  
  
   if ( result2 )  
      cout << "The character 'backslash-n' in the locale is "  
           << "a whitespace character." << endl;  
   else  
      cout << "The character 'backslash-n' in the locale is "  
           << " not a whitespace character." << endl;  
  
   if ( result3 )  
      cout << "The character ' ' in the locale is "  
           << "a whitespace character." << endl;  
   else  
      cout << "The character ' ' in the locale is "  
           << " not a whitespace character." << endl;  
}  
```  
  
##  <a name="isupper"></a>  isupper  
 Определяет, является ли элемент языкового стандарта символом в верхнем регистре.  
  
```  
template <class CharType>  
bool isupper(CharType Ch, const locale& Loc)  
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Проверяемый элемент.  
  
 `Loc`  
 Языковой стандарт, содержащий элемент для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если проверяемый элемент является символом в верхнем регистре; **false**, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон возвращает [use_facet](../standard-library/locale-functions.md#use_facet)< [ctype](../standard-library/ctype-class.md)\< **CharType**> >(`Loc`). [is](../standard-library/ctype-class.md#is)(**ctype**\< **CharType**>:: **upper**, `Ch`).  
  
### <a name="example"></a>Пример  
  
```cpp  
// locale_isupper.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   bool result1 = isupper ( 'L', loc );  
   bool result2 = isupper ( 'n', loc );  
   bool result3 = isupper ( '3', loc );  
  
   if ( result1 )  
      cout << "The character 'L' in the locale is "  
           << "a uppercase character." << endl;  
   else  
      cout << "The character 'L' in the locale is "  
           << " not a uppercase character." << endl;  
  
   if ( result2 )  
      cout << "The character 'n' in the locale is "  
           << "a uppercase character." << endl;  
   else  
      cout << "The character 'n' in the locale is "  
           << " not a uppercase character." << endl;  
  
   if ( result3 )  
      cout << "The character '3' in the locale is "  
           << "a uppercase character." << endl;  
   else  
      cout << "The character '3' in the locale is "  
           << " not a uppercase character." << endl;  
}  
```  
  
##  <a name="isxdigit"></a>  isxdigit  
 Определяет, является ли элемент языкового стандарта символом, используемым для представления шестнадцатеричных чисел.  
  
```  
template <class CharType>  
bool isxdigit(CharType Ch, const locale& Loc)  
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Проверяемый элемент.  
  
 `Loc`  
 Языковой стандарт, содержащий элемент для проверки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если проверяемый элемент является символом для записи шестнадцатеричных чисел; **false**, если это не так.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон возвращает [use_facet](../standard-library/locale-functions.md#use_facet)< [ctype](../standard-library/ctype-class.md)\< **CharType**> >(`Loc`). [is](../standard-library/ctype-class.md#is)(**ctype**\< **CharType**>:: **xdigit**, `Ch`).  
  
 В шестнадцатеричной системе для представления чисел используется база 16. С помощью цифр от 0 до 9, а также букв от A до F без учета регистра представляются десятичные числа от 0 до 15.  
  
### <a name="example"></a>Пример  
  
```cpp  
// locale_isxdigit.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   bool result1 = isxdigit ( '5', loc );  
   bool result2 = isxdigit ( 'd', loc );  
   bool result3 = isxdigit ( 'q', loc );  
  
   if ( result1 )  
      cout << "The character '5' in the locale is "  
           << "a hexidecimal digit-character." << endl;  
   else  
      cout << "The character '5' in the locale is "  
           << " not a hexidecimal digit-character." << endl;  
  
   if ( result2 )  
      cout << "The character 'd' in the locale is "  
           << "a hexidecimal digit-character." << endl;  
   else  
      cout << "The character 'd' in the locale is "  
           << " not a hexidecimal digit-character." << endl;  
  
   if ( result3 )  
      cout << "The character 'q' in the locale is "  
           << "a hexidecimal digit-character." << endl;  
   else  
      cout << "The character 'q' in the locale is "  
           << " not a hexidecimal digit-character." << endl;  
}  
```  
  
##  <a name="tolower"></a>  tolower  
 Преобразует символ в нижний регистр.  
  
```  
template <class CharType>  
CharType tolower(CharType Ch, const locale& Loc)  
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Символ для преобразования в нижний регистр.  
  
 `Loc`  
 Языковой стандарт, содержащий символ для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Символ, преобразованный в нижний регистр.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон возвращает [use_facet](../standard-library/locale-functions.md#use_facet)< [ctype](../standard-library/ctype-class.md)\< **CharType**> >(`Loc`). [tolower](../standard-library/ctype-class.md#tolower)(`Ch`).  
  
### <a name="example"></a>Пример  
  
```cpp  
// locale_tolower.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   char result1 = tolower ( 'H', loc );  
   cout << "The lower case of 'H' in the locale is: "  
        << result1 << "." << endl;  
   char result2 = tolower ( 'h', loc );  
   cout << "The lower case of 'h' in the locale is: "  
        << result2 << "." << endl;  
   char result3 = tolower ( '$', loc );  
   cout << "The lower case of '$' in the locale is: "  
        << result3 << "." << endl;  
}  
```  
  
##  <a name="toupper"></a>  toupper  
 Преобразует символ в верхний регистр.  
  
```  
template <class CharType>  
CharType toupper(CharType Ch, const locale& Loc)  
```  
  
### <a name="parameters"></a>Параметры  
 `Ch`  
 Символ для преобразования в верхний регистр.  
  
 `Loc`  
 Языковой стандарт, содержащий символ для преобразования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Символ, преобразованный в верхний регистр.  
  
### <a name="remarks"></a>Примечания  
 Функция-шаблон возвращает [use_facet](../standard-library/locale-functions.md#use_facet)< [ctype](../standard-library/ctype-class.md)\< **CharType**> >(`Loc`). [toupper](../standard-library/ctype-class.md#toupper)(`Ch`).  
  
### <a name="example"></a>Пример  
  
```cpp  
// locale_toupper.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc ( "German_Germany" );  
   char result1 = toupper ( 'h', loc );  
   cout << "The upper case of 'h' in the locale is: "  
        << result1 << "." << endl;  
   char result2 = toupper ( 'H', loc );  
   cout << "The upper case of 'H' in the locale is: "  
        << result2 << "." << endl;  
   char result3 = toupper ( '$', loc );  
   cout << "The upper case of '$' in the locale is: "  
        << result3 << "." << endl;  
}  
```  
  
##  <a name="use_facet"></a>  use_facet  
 Возвращает ссылку на аспект указанного типа, сохраненный в языковом стандарте.  
  
```  
template <class Facet>  
const Facet& use_facet(const locale& Loc);
```  
  
### <a name="parameters"></a>Параметры  
 `Loc`  
 Языковой стандарт const, содержащий тип аспекта, на который приведена ссылка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на аспект класса `Facet` внутри аргумента — языкового стандарта.  
  
### <a name="remarks"></a>Примечания  
 Ссылка на аспект, возвращаемая функцией-шаблоном, остается действительной, пока существует любая копия содержащего этот аспект языкового стандарта. Если в аргументе — языковом стандарте не перечислен такой объект — аспект класса `Facet`, функция создает исключение `bad_cast`.  
  
### <a name="example"></a>Пример  
  
```cpp  
// locale_use_facet.cpp  
// compile with: /EHsc  
#include <locale>  
#include <iostream>  
using namespace std;  
  
int main( )     
{  
   locale loc1 ( "German_Germany" ), loc2 ( "English_Australia" );  
   bool result1 = use_facet<ctype<char> > ( loc1 ).is(  
   ctype_base::alpha, 'a'   
);  
   bool result2 = use_facet<ctype<char> > ( loc2 ).is( ctype_base::alpha, '!'  
   );  
  
   if ( result1 )  
      cout << "The character 'a' in locale loc1 is alphabetic."   
           << endl;  
   else  
      cout << "The character 'a' in locale loc1 is not alphabetic."   
           << endl;  
  
   if ( result2 )  
      cout << "The character '!' in locale loc2 is alphabetic."   
           << endl;  
   else  
      cout << "The character '!' in locale loc2 is not alphabetic."   
           << endl;  
}  
```  
  
```Output  
The character 'a' in locale loc1 is alphabetic.  
The character '!' in locale loc2 is not alphabetic.  
```  
  
## <a name="see-also"></a>См. также  
 [\<locale>](../standard-library/locale.md)

