---
title: "Определения типов &lt;regex&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- cmatch
- std::cmatch
- regex/std::cmatch
- cregex_iterator
- std::cregex_iterator
- regex/std::cregex_iterator
- cregex_token_iterator
- std::cregex_token_iterator
- regex/std::cregex_token_iterator
- csub_match
- std::csub_match
- regex/std::csub_match
- regex
- std::regex
- regex/std::regex
- smatch
- std::smatch
- regex/std::smatch
- sregex_iterator
- std::sregex_iterator
- regex/std::sregex_iterator
- sregex_token_iterator
- std::sregex_token_iterator
- regex/std::sregex_token_iterator
- ssub_match
- std::ssub_match
- regex/std::ssub_match
- wcmatch
- std::wcmatch
- regex/std::wcmatch
- wcregex_iterator
- std::wcregex_iterator
- regex/std::wcregex_iterator
- wcregex_token_iterator
- std::wcregex_token_iterator
- regex/std::wcregex_token_iterator
- wcsub_match
- std::wcsub_match
- regex/std::wcsub_match
- wregex
- std::wregex
- regex/std::wregex
- wsmatch
- std::wsmatch
- regex/std::wsmatch
- wsregex_iterator
- std::wsregex_iterator
- regex/std::wsregex_iterator
- wsregex_token_iterator
- std::wsregex_token_iterator
- regex/std::wsregex_token_iterator
- wssub_match
- std::wssub_match
- regex/std::wssub_match
ms.assetid: e6a69067-106c-4a24-9e08-7c867a3a2260
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 41b445ceeeb1f37ee9873cb55f62d30d480d8718
ms.openlocfilehash: 60822dd232399b27ccda3db829b636d817091a2d
ms.lasthandoff: 02/24/2017

---
# <a name="ltregexgt-typedefs"></a>Определения типов &lt;regex&gt;
||||  
|-|-|-|  
|[Определение типа cmatch](#cmatch_typedef)|[Определение типа cregex_iterator](#cregex_iterator_typedef)|[Определение типа cregex_token_iterator](#cregex_token_iterator_typedef)|  
|[Определение типа csub_match](#csub_match_typedef)|[Определение типа regex](#regex_typedef)|[Определение типа smatch](#smatch_typedef)|  
|[Определение типа sregex_iterator](#sregex_iterator_typedef)|[Определение типа sregex_token_iterator](#sregex_token_iterator_typedef)|[Определение типа ssub_match](#ssub_match_typedef)|  
|[Определение типа wcmatch](#wcmatch_typedef)|[Определение типа wcregex_iterator](#wcregex_iterator_typedef)|[Определение типа wcregex_token_iterator](#wcregex_token_iterator_typedef)|  
|[Определение типа wcsub_match](#wcsub_match_typedef)|[Определение типа wregex](#wregex_typedef)|[Определение типа wsmatch](#wsmatch_typedef)|  
|[Определение типа wsregex_iterator](#wsregex_iterator_typedef)|[Определение типа wsregex_token_iterator](#wsregex_token_iterator_typedef)|[Определение типа wssub_match](#wssub_match_typedef)|  
  
##  <a name="a-namecmatchtypedefa--cmatch-typedef"></a><a name="cmatch_typedef"></a>  Определение типа cmatch  
 Определение типа для char match_results.  
  
```  
typedef match_results<const char*> cmatch;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс match_results](../standard-library/match-results-class.md) для итераторов типа `const char*`.  
  
##  <a name="a-namecregexiteratortypedefa--cregexiterator-typedef"></a><a name="cregex_iterator_typedef"></a>  Определение типа cregex_iterator  
 Определение типа для char regex_iterator.  
  
```  
typedef regex_iterator<const char*> cregex_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_iterator](../standard-library/regex-iterator-class.md) для итераторов типа `const char*`.  
  
##  <a name="a-namecregextokeniteratortypedefa--cregextokeniterator-typedef"></a><a name="cregex_token_iterator_typedef"></a>  Определение типа cregex_token_iterator  
 Определение типа для char regex_token_iterator  
  
```  
typedef regex_token_iterator<const char*> cregex_token_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md) для итераторов типа `const char*`.  
  
##  <a name="a-namecsubmatchtypedefa--csubmatch-typedef"></a><a name="csub_match_typedef"></a>  Определение типа csub_match  
 Определение типа для char sub_match.  
  
```  
typedef sub_match<const char*> csub_match;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс sub_match](../standard-library/sub-match-class.md) для итераторов типа `const char*`.  
  
##  <a name="a-nameregextypedefa--regex-typedef"></a><a name="regex_typedef"></a>  Определение типа regex Typedef  
 Определение типа для char basic_regex.  
  
```  
typedef basic_regex<char> regex;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс basic_regex](../standard-library/basic-regex-class.md) для итераторов типа `char`.  
  
> [!NOTE]
>  Символы старших разрядов будут иметь непредсказуемые результаты с `regex`. Значения вне диапазона от 0 до 127 могут привести к неопределенному поведению.  
  
##  <a name="a-namesmatchtypedefa--smatch-typedef"></a><a name="smatch_typedef"></a>  Определение типа smatch  
 Определение типа для string match_results.  
  
```  
typedef match_results<string::const_iterator> smatch;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс match_results](../standard-library/match-results-class.md) для итераторов типа `string::const_iterator`.  
  
##  <a name="a-namesregexiteratortypedefa--sregexiterator-typedef"></a><a name="sregex_iterator_typedef"></a>  Определение типа sregex_iterator  
 Определение типа для string regex_iterator.  
  
```  
typedef regex_iterator<string::const_iterator> sregex_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_iterator](../standard-library/regex-iterator-class.md) для итераторов типа `string::const_iterator`.  
  
##  <a name="a-namesregextokeniteratortypedefa--sregextokeniterator-typedef"></a><a name="sregex_token_iterator_typedef"></a>  Определение типа sregex_token_iterator  
 Определение типа для string regex_token_iterator.  
  
```  
typedef regex_token_iterator<string::const_iterator> sregex_token_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md) для итераторов типа `string::const_iterator`.  
  
##  <a name="a-namessubmatchtypedefa--ssubmatch-typedef"></a><a name="ssub_match_typedef"></a>  Определение типа ssub_match  
 Определение типа для string sub_match.  
  
```  
typedef sub_match<string::const_iterator> ssub_match;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс sub_match](../standard-library/sub-match-class.md) для итераторов типа `string::const_iterator`.  
  
##  <a name="a-namewcmatchtypedefa--wcmatch-typedef"></a><a name="wcmatch_typedef"></a>  Определение типа wcmatch  
 Определение типа для wchar_t match_results.  
  
```  
typedef match_results<const wchar_t *> wcmatch;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс match_results](../standard-library/match-results-class.md) для итераторов типа `const wchar_t*`.  
  
##  <a name="a-namewcregexiteratortypedefa--wcregexiterator-typedef"></a><a name="wcregex_iterator_typedef"></a>  Определение типа wcregex_iterator  
 Определение типа для wchar_t regex_iterator.  
  
```  
typedef regex_iterator<const wchar_t*> wcregex_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_iterator](../standard-library/regex-iterator-class.md) для итераторов типа `const wchar_t*`.  
  
##  <a name="a-namewcregextokeniteratortypedefa--wcregextokeniterator-typedef"></a><a name="wcregex_token_iterator_typedef"></a>  Определение типа wcregex_token_iterator  
 Определение типа для wchar_t regex_token_iterator.  
  
```  
typedef regex_token_iterator<const wchar_t*> wcregex_token_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md) для итераторов типа `const wchar_t*`.  
  
##  <a name="a-namewcsubmatchtypedefa--wcsubmatch-typedef"></a><a name="wcsub_match_typedef"></a>  Определение типа wcsub_match  
 Определение типа для wchar_t sub_match.  
  
```  
typedef sub_match<const wchar_t*> wcsub_match;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс sub_match](../standard-library/sub-match-class.md) для итераторов типа `const wchar_t*`.  
  
##  <a name="a-namewregextypedefa--wregex-typedef"></a><a name="wregex_typedef"></a>  Определение типа wregex  
 Определение типа для wchar_t basic_regex.  
  
```  
typedef basic_regex<wchar_t> wregex;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс basic_regex](../standard-library/basic-regex-class.md) для итераторов типа `wchar_t`.  
  
##  <a name="a-namewsmatchtypedefa--wsmatch-typedef"></a><a name="wsmatch_typedef"></a>  Определение типа wsmatch  
 Определение типа для wstring match_results.  
  
```  
typedef match_results<wstring::const_iterator> wsmatch;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс match_results](../standard-library/match-results-class.md) для итераторов типа `wstring::const_iterator`.  
  
##  <a name="a-namewsregexiteratortypedefa--wsregexiterator-typedef"></a><a name="wsregex_iterator_typedef"></a>  Определение типа wsregex_iterator  
 Определение типа для wstring regex_iterator.  
  
```  
typedef regex_iterator<wstring::const_iterator> wsregex_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_iterator](../standard-library/regex-iterator-class.md) для итераторов типа `wstring::const_iterator`.  
  
##  <a name="a-namewsregextokeniteratortypedefa--wsregextokeniterator-typedef"></a><a name="wsregex_token_iterator_typedef"></a>  Определение типа wsregex_token_iterator  
 Определение типа для wstring regex_token_iterator.  
  
```  
typedef regex_token_iterator<wstring::const_iterator> wsregex_token_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md) для итераторов типа `wstring::const_iterator`.  
  
##  <a name="a-namewssubmatchtypedefa--wssubmatch-typedef"></a><a name="wssub_match_typedef"></a>  Определение типа wssub_match  
 Определение типа для wstring sub_match.  
  
```  
typedef sub_match<wstring::const_iterator> wssub_match;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс sub_match](../standard-library/sub-match-class.md) для итераторов типа `wstring::const_iterator`.  
  
## <a name="see-also"></a>См. также  
[\<regex>](../standard-library/regex.md)  
[Класс regex_constants](../standard-library/regex-constants-class.md)  
[Класс regex_error](../standard-library/regex-error-class.md)  
[Функции \<regex>](../standard-library/regex-functions.md)  
[Класс regex_iterator](../standard-library/regex-iterator-class.md)  
[Операторы \<regex>](../standard-library/regex-operators.md)  
[Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)  
[Класс regex_traits](../standard-library/regex-traits-class.md)  

