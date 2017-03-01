---
title: "&lt;regex&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <regex>
dev_langs:
- C++
helpviewer_keywords:
- regex header
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
caps.latest.revision: 23
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
ms.sourcegitcommit: 248e9ba676b906af62f6804f4939e04158a8e2ef
ms.openlocfilehash: 4e172f8bf72fd528027c333cf411a307aa97d786
ms.lasthandoff: 02/24/2017

---
# <a name="ltregexgt"></a>&lt;regex&gt;
Определяет класс шаблона для синтаксического анализа [регулярных выражений](../standard-library/regular-expressions-cpp.md) и несколько классов шаблонов и функций для поиска в тексте совпадений с объектом регулярного выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <regex>  
```  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать объект регулярного выражения, используйте класс шаблона [Класс basic_regex](../standard-library/basic-regex-class.md) или одну из его специализаций ([regex](../standard-library/regex-typedefs.md#regex_typedef) и [wregex](../standard-library/regex-typedefs.md#wregex_typedef)) вместе с флагами синтаксиса типа [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#regex_constants__syntax_option_type).  
  
 Для поиска в тексте соответствий с объектом регулярного выражения используйте функции шаблона [regex_match](../standard-library/regex-functions.md#regex_match_function) и [regex_search](../standard-library/regex-functions.md#regex_search_function) вместе с флагами соответствия [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#regex_constants__match_flag_type). Эти функции возвращают результаты с использованием класса шаблонов [match_results Class](../standard-library/match-results-class.md) и его специализаций, [cmatch](../standard-library/regex-typedefs.md#cmatch_typedef), [wcmatch](../standard-library/regex-typedefs.md#wcmatch_typedef), [smatch](../standard-library/regex-typedefs.md#smatch_typedef) и [wsmatch](../standard-library/regex-typedefs.md#wsmatch_typedef), а также класса шаблона [Класс sub_match](../standard-library/sub-match-class.md) и его специализаций, [csub_match](../standard-library/regex-typedefs.md#csub_match_typedef), [wcsub_match](../standard-library/regex-typedefs.md#wcsub_match_typedef), [ssub_match](../standard-library/regex-typedefs.md#ssub_match_typedef) и [wssub_match](../standard-library/regex-typedefs.md#wssub_match_typedef).  
  
 Для замены текста, соответствующего объекту регулярного выражения, используйте функцию шаблона [regex_replace ](../standard-library/regex-functions.md#regex_replace_function) вместе с флагами соответствия типа [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#regex_constants__match_flag_type).  
  
 Чтобы выполнить итерацию нескольких соответствий объекта регулярного выражения, используйте классы шаблона [Класс regex_iterator](../standard-library/regex-iterator-class.md) и [Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md) или одну из их специализаций, [cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator_typedef), [sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator_typedef), [wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator_typedef), [wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator_typedef), [cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator_typedef), [sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator_typedef), [wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator_typedef) или [wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator_typedef), вместе с флагами соответствия типа [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#regex_constants__match_flag_type).  
  
 Чтобы изменить сведения о грамматике регулярных выражений, напишите класс, реализующий характеристики регулярного выражения.  
  
### <a name="classes"></a>Классы  
  
|||  
|-|-|  
|[basic_regex](../standard-library/basic-regex-class.md)|Создание оболочки для регулярного выражения.|  
|[match_results](../standard-library/match-results-class.md)|Содержит последовательность подстрок соответствия.|  
|[regex_constants](../standard-library/regex-constants-class.md)|Содержит различные константы.|  
|[regex_error](../standard-library/regex-error-class.md)|Сообщает о недопустимом регулярном выражении.|  
|[regex_iterator](../standard-library/regex-iterator-class.md)|Перебирает результаты сопоставления.|  
|[regex_traits](../standard-library/regex-traits-class.md)|Описывает характеристики элементов для сопоставления.|  
|[regex_traits\<char>](../standard-library/regex-traits-char-class.md)|Описывает характеристики `char` для сопоставления.|  
|[regex_traits<wchar_t>](../standard-library/regex-traits-wchar-t-class.md)|Описывает характеристики `wchar_t` для сопоставления.|  
|[regex_token_iterator](../standard-library/regex-token-iterator-class.md)|Перебирает подстроки соответствия.|  
|[sub_match](../standard-library/sub-match-class.md)|Описывает подстроку соответствия.|  
  
### <a name="type-definitions"></a>Определения типов  
  
|||  
|-|-|  
|[cmatch](../standard-library/regex-typedefs.md#cmatch_typedef)|Определение типа для `char``match_results`.|  
|[cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator_typedef)|Определение типа для `char``regex_iterator`.|  
|[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator_typedef)|Определение типа для `char``regex_token_iterator`.|  
|[csub_match](../standard-library/regex-typedefs.md#csub_match_typedef)|Определение типа для `char``sub_match`.|  
|[regex](../standard-library/regex-typedefs.md#regex_typedef)|Определение типа для `char``basic_regex`.|  
|[smatch](../standard-library/regex-typedefs.md#smatch_typedef)|Определение типа для `string``match_results`.|  
|[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator_typedef)|Определение типа для `string``regex_iterator`.|  
|[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator_typedef)|Определение типа для `string``regex_token_iterator`.|  
|[ssub_match](../standard-library/regex-typedefs.md#ssub_match_typedef)|Определение типа для `string``sub_match`.|  
|[wcmatch](../standard-library/regex-typedefs.md#wcmatch_typedef)|Определение типа для `wchar_t``match_results`.|  
|[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator_typedef)|Определение типа для `wchar_t``regex_iterator`.|  
|[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator_typedef)|Определение типа для `wchar_t``regex_token_iterator`.|  
|[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match_typedef)|Определение типа для `wchar_t``sub_match`.|  
|[wregex](../standard-library/regex-typedefs.md#wregex_typedef)|Определение типа для `wchar_t``basic_regex`.|  
|[wsmatch](../standard-library/regex-typedefs.md#wsmatch_typedef)|Определение типа для `wstring``match_results`.|  
|[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator_typedef)|Определение типа для `wstring``regex_iterator`.|  
|[wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator_typedef)|Определение типа для `wstring``regex_token_iterator`.|  
|[wssub_match](../standard-library/regex-typedefs.md#wssub_match_typedef)|Определение типа для `wstring``sub_match`.|  
  
### <a name="functions"></a>Функции  
  
|||  
|-|-|  
|[regex_match](../standard-library/regex-functions.md#regex_match_function)|Точно соответствует регулярному выражению.|  
|[regex_replace](../standard-library/regex-functions.md#regex_replace_function)|Заменяет соответствующие регулярные выражения.|  
|[regex_search](../standard-library/regex-functions.md#regex_search_function)|Поиск соответствия регулярному выражению.|  
|[swap](../standard-library/regex-functions.md#swap_function)|Меняет местами объекты `basic_regex` и `match_results`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор==](../standard-library/regex-operators.md#operator_eq_eq)|Сравнение различных объектов, равенство.|  
|[оператор!=](../standard-library/regex-operators.md#operator_neq)|Сравнение различных объектов, неравенство.|  
|[оператор<](../standard-library/regex-operators.md#operator_lt_)|Сравнение различных объектов, меньше.|  
|[оператор\<=](../standard-library/regex-operators.md#operator_lt__eq)|Сравнение различных объектов, меньше или равно.|  
|[оператор>](../standard-library/regex-operators.md#operator_gt_)|Сравнение различных объектов, больше.|  
|[оператор>=](../standard-library/regex-operators.md#operator_gt__eq)|Сравнение различных объектов, больше или равно.|  
|[оператор<<](../standard-library/regex-operators.md#operator_lt__lt_)|Вставляет `sub_match` в поток.|  
  
## <a name="see-also"></a>См. также  
[Регулярные выражения (C++)](../standard-library/regular-expressions-cpp.md)  
[Класс regex_constants](../standard-library/regex-constants-class.md)  
[Класс regex_error](../standard-library/regex-error-class.md)  
[Функции \<regex>](../standard-library/regex-functions.md)  
[Класс regex_iterator](../standard-library/regex-iterator-class.md)  
[Операторы \<regex>](../standard-library/regex-operators.md)  
[Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)  
[Класс regex_traits](../standard-library/regex-traits-class.md)  
[Определения типов \<regex>](../standard-library/regex-typedefs.md)  




