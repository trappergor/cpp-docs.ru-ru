---
title: "&lt;regex&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<regex>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "regex - заголовок [TR1]"
ms.assetid: 5dd4ef74-6063-4dbc-b692-1960bb736f0b
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# &lt;regex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет класс шаблона для синтаксического анализа [Регулярные выражения \(C\+\+\)](../standard-library/regular-expressions-cpp.md) и несколько классов шаблонов и функций для поиска в тексте совпадений с объектом регулярного выражения.  
  
## Синтаксис  
  
```  
#include <regex>  
```  
  
## Заметки  
 Чтобы создать объект регулярного выражения, используйте класс шаблона [Класс basic\_regex](../Topic/basic_regex%20Class.md) или одну из его специализаций, [Определение типа \(Typedef\) regex](../Topic/regex%20Typedef.md) и [Определение типа \(Typedef\) wregex](../Topic/wregex%20Typedef.md), вместе с флагами синтаксиса типа [regex\_constants::syntax\_option\_type](../Topic/regex_constants::syntax_option_type.md).  
  
 Для поиска в тексте соответствий с объектом регулярного выражения используйте функции шаблона [Функция regex\_match](../Topic/regex_match%20Function.md) и [Функция regex\_search](../Topic/regex_search%20Function.md) вместе с флагами соответствия типа [regex\_constants::match\_flag\_type](../Topic/regex_constants::match_flag_type.md).  Эти функции возвращают результаты, используя класс шаблона [Класс match\_results](../standard-library/match-results-class.md) и его специализации, [Определение типа cmatch](../Topic/cmatch%20Typedef.md), [Определение типа \(Typedef\) wcmatch](../Topic/wcmatch%20Typedef.md), [Определение типа \(Typedef\) smatch](../Topic/smatch%20Typedef.md) и [Определение типа \(Typedef\) wsmatch](../Topic/wsmatch%20Typedef.md), вместе с классом шаблона [Класс sub\_match](../standard-library/sub-match-class.md) и его специализациями, [Определение типа \(Typedef\) csub\_match](../Topic/csub_match%20Typedef.md), [Определение типа \(Typedef\) wcsub\_match](../Topic/wcsub_match%20Typedef.md), [Определение типа \(Typedef\) ssub\_match](../Topic/ssub_match%20Typedef.md) и [Определение типа wssub\_match](../Topic/wssub_match%20Typedef.md).  
  
 Для замены текста, соответствующего объекту регулярного выражения, используйте функцию шаблона [Функция regex\_replace](../Topic/regex_replace%20Function.md) вместе с флагами соответствия типа [regex\_constants::match\_flag\_type](../Topic/regex_constants::match_flag_type.md).  
  
 Для перебора нескольких соответствий объекту регулярного выражения используйте классы шаблонов [Класс regex\_iterator](../standard-library/regex-iterator-class.md) и [Класс regex\_token\_iterator](../Topic/regex_token_iterator%20Class.md) или одну из их специализаций, [Определение типа \(Typedef\) cregex\_iterator](../Topic/cregex_iterator%20Typedef.md), [Определение типа sregex\_iterator](../Topic/sregex_iterator%20Typedef.md), [Определение типа wcregex\_iterator](../Topic/wcregex_iterator%20Typedef.md), [Определение типа \(Typedef\) wsregex\_iterator](../Topic/wsregex_iterator%20Typedef.md), [Определение типа cregex\_token\_iterator](../Topic/cregex_token_iterator%20Typedef.md), [Определение типа \(Typedef\) sregex\_token\_iterator](../Topic/sregex_token_iterator%20Typedef.md), [Определение типа \(Typedef\) wcregex\_token\_iterator](../Topic/wcregex_token_iterator%20Typedef.md) или [Определение типа \(Typedef\) wsregex\_token\_iterator](../Topic/wsregex_token_iterator%20Typedef.md), вместе с флагами соответствия типа [regex\_constants::match\_flag\_type](../Topic/regex_constants::match_flag_type.md).  
  
 Чтобы изменить сведения о грамматике регулярных выражений, напишите класс, реализующий характеристики регулярного выражения.  
  
### Классы  
  
|||  
|-|-|  
|[basic\_regex](../Topic/basic_regex%20Class.md)|Создание оболочки для регулярного выражения.|  
|[match\_results](../standard-library/match-results-class.md)|Содержит последовательность подстрок соответствия.|  
|[regex\_constants](../Topic/regex_constants%20Class.md)|Содержит различные константы.|  
|[regex\_error](../standard-library/regex-error-class.md)|Сообщает о недопустимом регулярном выражении.|  
|[regex\_iterator](../standard-library/regex-iterator-class.md)|Перебирает результаты сопоставления.|  
|[regex\_traits](../standard-library/regex-traits-class.md)|Описывает характеристики элементов для сопоставления.|  
|[regex\_traits\<char\>](../standard-library/regex-traits-char-class.md)|Описывает характеристики `char` для сопоставления.|  
|[regex\_traits\<wchar\_t\>](../standard-library/regex-traits-wchar-t-class.md)|Описывает характеристики `wchar_t` для сопоставления.|  
|[regex\_token\_iterator](../Topic/regex_token_iterator%20Class.md)|Перебирает подстроки соответствия.|  
|[sub\_match](../standard-library/sub-match-class.md)|Описывает подстроку соответствия.|  
  
### Определения типов  
  
|||  
|-|-|  
|[cmatch](../Topic/cmatch%20Typedef.md)|Определение типа `char` `match_results`.|  
|[cregex\_iterator](../Topic/cregex_iterator%20Typedef.md)|Определение типа `char` `regex_iterator`.|  
|[cregex\_token\_iterator](../Topic/cregex_token_iterator%20Typedef.md)|Определение типа `char` `regex_token_iterator`.|  
|[csub\_match](../Topic/csub_match%20Typedef.md)|Определение типа `char` `sub_match`.|  
|[regex](../Topic/regex%20Typedef.md)|Определение типа `char` `basic_regex`.|  
|[smatch](../Topic/smatch%20Typedef.md)|Определение типа `string` `match_results`.|  
|[sregex\_iterator](../Topic/sregex_iterator%20Typedef.md)|Определение типа `string` `regex_iterator`.|  
|[sregex\_token\_iterator](../Topic/sregex_token_iterator%20Typedef.md)|Определение типа `string` `regex_token_iterator`.|  
|[ssub\_match](../Topic/ssub_match%20Typedef.md)|Определение типа `string` `sub_match`.|  
|[wcmatch](../Topic/wcmatch%20Typedef.md)|Определение типа `wchar_t` `match_results`.|  
|[wcregex\_iterator](../Topic/wcregex_iterator%20Typedef.md)|Определение типа `wchar_t` `regex_iterator`.|  
|[wcregex\_token\_iterator](../Topic/wcregex_token_iterator%20Typedef.md)|Определение типа `wchar_t` `regex_token_iterator`.|  
|[wcsub\_match](../Topic/wcsub_match%20Typedef.md)|Определение типа `wchar_t` `sub_match`.|  
|[wregex](../Topic/wregex%20Typedef.md)|Определение типа `wchar_t` `basic_regex`.|  
|[wsmatch](../Topic/wsmatch%20Typedef.md)|Определение типа `wstring` `match_results`.|  
|[wsregex\_iterator](../Topic/wsregex_iterator%20Typedef.md)|Определение типа `wstring` `regex_iterator`.|  
|[wsregex\_token\_iterator](../Topic/wsregex_token_iterator%20Typedef.md)|Определение типа `wstring` `regex_token_iterator`.|  
|[wssub\_match](../Topic/wssub_match%20Typedef.md)|Определение типа `wstring` `sub_match`.|  
  
### Функции  
  
|||  
|-|-|  
|[regex\_match](../Topic/regex_match%20Function.md)|Точно соответствует регулярному выражению.|  
|[regex\_replace](../Topic/regex_replace%20Function.md)|Заменяет соответствующие регулярные выражения.|  
|[regex\_search](../Topic/regex_search%20Function.md)|Поиск соответствия регулярному выражению.|  
|[swap](../Topic/swap%20Function%20%3Cregex%3E.md)|Меняет местами объекты `basic_regex` и `match_results`.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\=\=](../Topic/operator==%20%3Cregex%3E.md)|Сравнение различных объектов, равенство.|  
|[operator\!\=](../Topic/operator!=%20%3Cregex%3E.md)|Сравнение различных объектов, неравенство.|  
|[Оператор \<](../Topic/operator%3C%20%3Cregex%3E.md)|Сравнение различных объектов, меньше.|  
|[Оператор \<\=](../Topic/operator%3C=%20%3Cregex%3E.md)|Сравнение различных объектов, меньше или равно.|  
|[Оператор \>](../Topic/operator%3E%20%3Cregex%3E.md)|Сравнение различных объектов, больше.|  
|[Оператор \>\=](../Topic/operator%3E=%20%3Cregex%3E.md)|Сравнение различных объектов, больше или равно.|  
|[\<\< \- оператор](../Topic/operator%3C%3C%20%3Cregex%3E.md)|Вставляет `sub_match` в поток.|  
  
## См. также  
 [Регулярные выражения \(C\+\+\)](../standard-library/regular-expressions-cpp.md)