---
title: "&lt;regex&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <regex>
dev_langs:
- C++
helpviewer_keywords:
- regex header
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c586cf909ce07f17dfdba08005d1efd8489db869
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ltregexgt"></a>&lt;regex&gt;
Определяет класс шаблона для синтаксического анализа [регулярных выражений](../standard-library/regular-expressions-cpp.md) и несколько классов шаблонов и функций для поиска в тексте совпадений с объектом регулярного выражения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#include <regex>  
```  
  
## <a name="remarks"></a>Примечания  
 Чтобы создать объект регулярного выражения, используйте класс шаблона [Класс basic_regex](../standard-library/basic-regex-class.md) или одну из его специализаций ([regex](../standard-library/regex-typedefs.md#regex) и [wregex](../standard-library/regex-typedefs.md#wregex)) вместе с флагами синтаксиса типа [regex_constants::syntax_option_type](../standard-library/regex-constants-class.md#syntax_option_type).  
  
 Для поиска в тексте совпадений с объектом регулярного выражения, используйте функции шаблона [regex_match](../standard-library/regex-functions.md#regex_match) и [regex_search](../standard-library/regex-functions.md#regex_search)вместе с флагами соответствия типа [regex_constants::match_ flag_type](../standard-library/regex-constants-class.md#match_flag_type). Эти функции возвращают результаты с использованием класса шаблонов [match_results Class](../standard-library/match-results-class.md) и его специализаций, [cmatch](../standard-library/regex-typedefs.md#cmatch), [wcmatch](../standard-library/regex-typedefs.md#wcmatch), [smatch](../standard-library/regex-typedefs.md#smatch) и [wsmatch](../standard-library/regex-typedefs.md#wsmatch), а также класса шаблона [Класс sub_match](../standard-library/sub-match-class.md) и его специализаций, [csub_match](../standard-library/regex-typedefs.md#csub_match), [wcsub_match](../standard-library/regex-typedefs.md#wcsub_match), [ssub_match](../standard-library/regex-typedefs.md#ssub_match) и [wssub_match](../standard-library/regex-typedefs.md#wssub_match).  
  
 Чтобы заменить текст, соответствующий объект регулярного выражения, используйте функцию шаблона [regex_replace](../standard-library/regex-functions.md#regex_replace)вместе с флагами соответствия типа [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#match_flag_type).  
  
 Чтобы выполнить итерацию нескольких соответствий объекта регулярного выражения, используйте классы шаблона [Класс regex_iterator](../standard-library/regex-iterator-class.md) и [Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md) или одну из их специализаций, [cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator), [sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator), [wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator), [wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator), [cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator), [sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator), [wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator) или [wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator), вместе с флагами соответствия типа [regex_constants::match_flag_type](../standard-library/regex-constants-class.md#match_flag_type).  
  
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
|[cmatch](../standard-library/regex-typedefs.md#cmatch)|Определение типа `char` `match_results`.|  
|[cregex_iterator](../standard-library/regex-typedefs.md#cregex_iterator)|Определение типа `char` `regex_iterator`.|  
|[cregex_token_iterator](../standard-library/regex-typedefs.md#cregex_token_iterator)|Определение типа `char` `regex_token_iterator`.|  
|[csub_match](../standard-library/regex-typedefs.md#csub_match)|Определение типа `char` `sub_match`.|  
|[regex](../standard-library/regex-typedefs.md#regex)|Определение типа `char` `basic_regex`.|  
|[smatch](../standard-library/regex-typedefs.md#smatch)|Определение типа `string` `match_results`.|  
|[sregex_iterator](../standard-library/regex-typedefs.md#sregex_iterator)|Определение типа `string` `regex_iterator`.|  
|[sregex_token_iterator](../standard-library/regex-typedefs.md#sregex_token_iterator)|Определение типа `string` `regex_token_iterator`.|  
|[ssub_match](../standard-library/regex-typedefs.md#ssub_match)|Определение типа `string` `sub_match`.|  
|[wcmatch](../standard-library/regex-typedefs.md#wcmatch)|Определение типа `wchar_t` `match_results`.|  
|[wcregex_iterator](../standard-library/regex-typedefs.md#wcregex_iterator)|Определение типа `wchar_t` `regex_iterator`.|  
|[wcregex_token_iterator](../standard-library/regex-typedefs.md#wcregex_token_iterator)|Определение типа `wchar_t` `regex_token_iterator`.|  
|[wcsub_match](../standard-library/regex-typedefs.md#wcsub_match)|Определение типа `wchar_t` `sub_match`.|  
|[wregex](../standard-library/regex-typedefs.md#wregex)|Определение типа `wchar_t` `basic_regex`.|  
|[wsmatch](../standard-library/regex-typedefs.md#wsmatch)|Определение типа `wstring` `match_results`.|  
|[wsregex_iterator](../standard-library/regex-typedefs.md#wsregex_iterator)|Определение типа `wstring` `regex_iterator`.|  
|[wsregex_token_iterator](../standard-library/regex-typedefs.md#wsregex_token_iterator)|Определение типа `wstring` `regex_token_iterator`.|  
|[wssub_match](../standard-library/regex-typedefs.md#wssub_match)|Определение типа `wstring` `sub_match`.|  
  
### <a name="functions"></a>Функции  
  
|||  
|-|-|  
|[regex_match](../standard-library/regex-functions.md#regex_match)|Точно соответствует регулярному выражению.|  
|[regex_replace](../standard-library/regex-functions.md#regex_replace)|Заменяет соответствующие регулярные выражения.|  
|[regex_search](../standard-library/regex-functions.md#regex_search)|Поиск соответствия регулярному выражению.|  
|[swap](../standard-library/regex-functions.md#swap)|Меняет местами объекты `basic_regex` и `match_results`.|  
  
### <a name="operators"></a>Операторы  
  
|||  
|-|-|  
|[оператор==](../standard-library/regex-operators.md#op_eq_eq)|Сравнение различных объектов, равенство.|  
|[оператор!=](../standard-library/regex-operators.md#op_neq)|Сравнение различных объектов, неравенство.|  
|[оператор<](../standard-library/regex-operators.md#op_lt)|Сравнение различных объектов, меньше.|  
|[operator\<=](../standard-library/regex-operators.md#op_gt_eq)|Сравнение различных объектов, меньше или равно.|  
|[оператор>](../standard-library/regex-operators.md#op_gt)|Сравнение различных объектов, больше.|  
|[оператор>=](../standard-library/regex-operators.md#op_gt_eq)|Сравнение различных объектов, больше или равно.|  
|[оператор<<](../standard-library/regex-operators.md#op_lt_lt)|Вставляет `sub_match` в поток.|  
  
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



