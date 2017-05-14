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
- regex/std::cmatch
- cregex_iterator
- regex/std::cregex_iterator
- cregex_token_iterator
- regex/std::cregex_token_iterator
- csub_match
- regex/std::csub_match
- regex
- regex/std::regex
- smatch
- regex/std::smatch
- sregex_iterator
- regex/std::sregex_iterator
- sregex_token_iterator
- regex/std::sregex_token_iterator
- ssub_match
- regex/std::ssub_match
- wcmatch
- regex/std::wcmatch
- wcregex_iterator
- regex/std::wcregex_iterator
- wcregex_token_iterator
- regex/std::wcregex_token_iterator
- wcsub_match
- regex/std::wcsub_match
- wregex
- regex/std::wregex
- wsmatch
- regex/std::wsmatch
- wsregex_iterator
- regex/std::wsregex_iterator
- wsregex_token_iterator
- regex/std::wsregex_token_iterator
- wssub_match
- regex/std::wssub_match
dev_langs:
- C++
ms.assetid: e6a69067-106c-4a24-9e08-7c867a3a2260
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 99e7c52466e94e34af0fa2e933e8c9132a440e3c
ms.contentlocale: ru-ru
ms.lasthandoff: 04/19/2017

---
# <a name="ltregexgt-typedefs"></a>Определения типов &lt;regex&gt;
||||  
|-|-|-|  
|[cmatch](#cmatch)|[cregex_iterator](#cregex_iterator)|[cregex_token_iterator](#cregex_token_iterator)|  
|[csub_match](#csub_match)|[regex](#regex)|[smatch](#smatch)|  
|[sregex_iterator](#sregex_iterator)|[sregex_token_iterator](#sregex_token_iterator)|[ssub_match](#ssub_match)|  
|[wcmatch](#wcmatch)|[wcregex_iterator](#wcregex_iterator)|[wcregex_token_iterator](#wcregex_token_iterator)|  
|[wcsub_match](#wcsub_match)|[wregex](#wregex)|[wsmatch](#wsmatch)|  
|[wsregex_iterator](#wsregex_iterator)|[wsregex_token_iterator](#wsregex_token_iterator)|[wssub_match](#wssub_match)|  
  
##  <a name="cmatch"></a>  Определение типа cmatch  
 Определение типа для char match_results.  
  
```  
typedef match_results<const char*> cmatch;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс match_results](../standard-library/match-results-class.md) для итераторов типа `const char*`.  
  
##  <a name="cregex_iterator"></a>  Определение типа cregex_iterator  
 Определение типа для char regex_iterator.  
  
```  
typedef regex_iterator<const char*> cregex_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_iterator](../standard-library/regex-iterator-class.md) для итераторов типа `const char*`.  
  
##  <a name="cregex_token_iterator"></a>  Определение типа cregex_token_iterator  
 Определение типа для char regex_token_iterator  
  
```  
typedef regex_token_iterator<const char*> cregex_token_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md) для итераторов типа `const char*`.  
  
##  <a name="csub_match"></a>  Определение типа csub_match  
 Определение типа для char sub_match.  
  
```  
typedef sub_match<const char*> csub_match;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс sub_match](../standard-library/sub-match-class.md) для итераторов типа `const char*`.  
  
##  <a name="regex"></a>  Определение типа regex Typedef  
 Определение типа для char basic_regex.  
  
```  
typedef basic_regex<char> regex;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс basic_regex](../standard-library/basic-regex-class.md) для итераторов типа `char`.  
  
> [!NOTE]
>  Символы старших разрядов будут иметь непредсказуемые результаты с `regex`. Значения вне диапазона от 0 до 127 могут привести к неопределенному поведению.  
  
##  <a name="smatch"></a>  Определение типа smatch  
 Определение типа для string match_results.  
  
```  
typedef match_results<string::const_iterator> smatch;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс match_results](../standard-library/match-results-class.md) для итераторов типа `string::const_iterator`.  
  
##  <a name="sregex_iterator"></a>  Определение типа sregex_iterator  
 Определение типа для string regex_iterator.  
  
```  
typedef regex_iterator<string::const_iterator> sregex_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_iterator](../standard-library/regex-iterator-class.md) для итераторов типа `string::const_iterator`.  
  
##  <a name="sregex_token_iterator"></a>  Определение типа sregex_token_iterator  
 Определение типа для string regex_token_iterator.  
  
```  
typedef regex_token_iterator<string::const_iterator> sregex_token_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md) для итераторов типа `string::const_iterator`.  
  
##  <a name="ssub_match"></a>  Определение типа ssub_match  
 Определение типа для string sub_match.  
  
```  
typedef sub_match<string::const_iterator> ssub_match;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс sub_match](../standard-library/sub-match-class.md) для итераторов типа `string::const_iterator`.  
  
##  <a name="wcmatch"></a>  Определение типа wcmatch  
 Определение типа для wchar_t match_results.  
  
```  
typedef match_results<const wchar_t *> wcmatch;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс match_results](../standard-library/match-results-class.md) для итераторов типа `const wchar_t*`.  
  
##  <a name="wcregex_iterator"></a>  Определение типа wcregex_iterator  
 Определение типа для wchar_t regex_iterator.  
  
```  
typedef regex_iterator<const wchar_t*> wcregex_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_iterator](../standard-library/regex-iterator-class.md) для итераторов типа `const wchar_t*`.  
  
##  <a name="wcregex_token_iterator"></a>  Определение типа wcregex_token_iterator  
 Определение типа для wchar_t regex_token_iterator.  
  
```  
typedef regex_token_iterator<const wchar_t*> wcregex_token_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md) для итераторов типа `const wchar_t*`.  
  
##  <a name="wcsub_match"></a>  Определение типа wcsub_match  
 Определение типа для wchar_t sub_match.  
  
```  
typedef sub_match<const wchar_t*> wcsub_match;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс sub_match](../standard-library/sub-match-class.md) для итераторов типа `const wchar_t*`.  
  
##  <a name="wregex"></a>  Определение типа wregex  
 Определение типа для wchar_t basic_regex.  
  
```  
typedef basic_regex<wchar_t> wregex;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс basic_regex](../standard-library/basic-regex-class.md) для итераторов типа `wchar_t`.  
  
##  <a name="wsmatch"></a>  Определение типа wsmatch  
 Определение типа для wstring match_results.  
  
```  
typedef match_results<wstring::const_iterator> wsmatch;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс match_results](../standard-library/match-results-class.md) для итераторов типа `wstring::const_iterator`.  
  
##  <a name="wsregex_iterator"></a>  Определение типа wsregex_iterator  
 Определение типа для wstring regex_iterator.  
  
```  
typedef regex_iterator<wstring::const_iterator> wsregex_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_iterator](../standard-library/regex-iterator-class.md) для итераторов типа `wstring::const_iterator`.  
  
##  <a name="wsregex_token_iterator"></a>  Определение типа wsregex_token_iterator  
 Определение типа для wstring regex_token_iterator.  
  
```  
typedef regex_token_iterator<wstring::const_iterator> wsregex_token_iterator;  
```  
  
### <a name="remarks"></a>Примечания  
 Тип описывает специализацию класса-шаблона [Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md) для итераторов типа `wstring::const_iterator`.  
  
##  <a name="wssub_match"></a>  Определение типа wssub_match  
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

