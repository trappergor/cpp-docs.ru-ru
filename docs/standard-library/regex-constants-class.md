---
title: "Класс regex_constants | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- regex_constants
- regex/std::regex_constants
- error_collate
- regex/std::regex_constants::error_collate
- error_ctype
- regex/std::regex_constants::error_ctype
- error_escape
- regex/std::regex_constants::error_escape
- error_backref
- regex/std::regex_constants::error_backref
- error_brack
- regex/std::regex_constants::error_brack
- error_paren
- regex/std::regex_constants::error_paren
- error_brace
- regex/std::regex_constants::error_brace
- error_badbrace
- regex/std::regex_constants::error_badbrace
- error_range
- regex/std::regex_constants::error_range
- error_space
- regex/std::regex_constants::error_space
- error_badrepeat
- regex/std::regex_constants::error_badrepeat
- error_complexity
- regex/std::regex_constants::error_complexity
- error_stack
- regex/std::regex_constants::error_stack
- error_parse
- regex/std::regex_constants::error_parse
- error_syntax
- regex/std::regex_constants::error_syntax
- match_default
- regex/std::regex_constants::match_default
- match_not_bol
- regex/std::regex_constants::match_not_bol
- match_not_eol
- regex/std::regex_constants::match_not_eol
- match_not_bow
- regex/std::regex_constants::match_not_bow
- match_not_eow
- regex/std::regex_constants::match_not_eow
- match_any
- regex/std::regex_constants::match_any
- match_not_null
- regex/std::regex_constants::match_not_null
- match_continuous
- regex/std::regex_constants::match_continuous
- match_prev_avail
- regex/std::regex_constants::match_prev_avail
- format_default
- regex/std::regex_constants::format_default
- format_sed
- regex/std::regex_constants::format_sed
- format_no_copy
- regex/std::regex_constants::format_no_copy
- format_first_only
- regex/std::regex_constants::format_first_only
- regex/std::regex_constants::ECMAScript
- regex/std::regex_constants::basic
- regex/std::regex_constants::extended
- regex/std::regex_constants::awk
- regex/std::regex_constants::grep
- regex/std::regex_constants::egrep
- regex/std::regex_constants::icase
- regex/std::regex_constants::nosubs
- regex/std::regex_constants::optimize
- regex/std::regex_constants::collate
dev_langs:
- C++
helpviewer_keywords:
- regex_constants class
ms.assetid: 4a69c0ba-c46d-46e4-bd29-6f4efb805f26
caps.latest.revision: 18
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 83cf6d3c8b6c571898bf6d1f2aeeefbc930dd573
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="regexconstants-class"></a>Класс regex_constants
Пространство имен для флажков регулярных выражений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace regex_constants {  
    enum syntax_option_type;  
    enum match_flag_type;  
    enum error_type;  
 }  
```  
  
## <a name="remarks"></a>Примечания  
 Пространство имен `regex_constants` инкапсулирует несколько типов флажков и соответствующих им значений флажков.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<regex>  
  
 **Пространство имен:** std  
  
##  <a name="error_type"></a>  regex_constants::error_type  
 Флаги для оповещения об ошибках синтаксиса регулярного выражения.  
  
```  
enum error_type
    {    // identify error
    error_collate,
    error_ctype,
    error_escape,
    error_backref,
    error_brack,
    error_paren,
    error_brace,
    error_badbrace,
    error_range,
    error_space,
    error_badrepeat,
    error_complexity,
    error_stack,
    error_parse,
    error_syntax
    };  
```  
  
### <a name="remarks"></a>Примечания  
 Тип представляет собой перечисляемый тип, описывающий объект, который может содержать флаги ошибок. Ниже перечислены значения различных флагов.  
  
 `error_backref` -- выражение содержит недопустимую обратную ссылку  
  
 `error_badbrace` -- выражение содержит недопустимое число в выражении { }  
  
 `error_badrepeat` -- выражение повторения (в большинстве контекстов одно из "*", "", "+", "{") не имеет перед собой выражения  
  
 `error_brace` -- выражение содержит непарные "{" или "}"  
  
 `error_brack` -- выражение содержит непарные "[" или "]"  
  
 `error_collate` -- выражение содержит недопустимое имя элемента сортировки  
  
 `error_complexity` -- попытка сопоставления не удалась из-за излишней сложности  
  
 `error_ctype` -- выражение содержит недопустимое имя класса символа  
  
 `error_escape` -- выражение содержит недопустимую последовательность отмены  
  
 `error_paren` -- выражение содержит непарные "(" или ")"  
  
 `error_parse` -- не удалось распознать выражение  
  
 `error_range` -- выражение содержит недопустимый спецификатор диапазона символов  
  
 `error_space` -- распознавание регулярного выражения не удалось из-за недостатка ресурсов  
  
 `error_stack` -- попытка сопоставления не удалась из-за недостатка памяти  
  
 `error_syntax` -- распознавание не удалось из-за синтаксической ошибки  
  
 `error_backref` -- выражение содержит недопустимую обратную ссылку  
  
##  <a name="match_flag_type"></a>  regex_constants::match_flag_type  
 Флаги для параметров сопоставления регулярного выражения.  
  
```  
enum match_flag_type 
    {    // specify matching and formatting rules
    match_default = 0x0000,
    match_not_bol = 0x0001,
    match_not_eol = 0x0002,
    match_not_bow = 0x0004,
    match_not_eow = 0x0008,
    match_any = 0x0010,
    match_not_null = 0x0020,
    match_continuous = 0x0040,
    match_prev_avail = 0x0100,
    format_default = 0x0000,
    format_sed = 0x0400,
    format_no_copy = 0x0800,
    format_first_only = 0x1000,
    _Match_not_null = 0x2000
    };  
```  
  
### <a name="remarks"></a>Примечания  
 Тип является типом битовой маски, описывающим параметры для использования при сопоставлении текстовой последовательности с регулярным выражением и флаги формата для использования при замене текста. Параметры можно использовать вместе с `|`.  
  
 Параметры сопоставления  
  
 `match_default`  
  
 `match_not_bol` -- не рассматривать первую позицию в последовательности-результате как начало строки  
  
 `match_not_eol` -- не рассматривать позицию после конца в последовательности-результате как конец строки  
  
 `match_not_bow` -- не рассматривать первую позицию в последовательности-результате как начало слова  
  
 `match_not_eow` -- не рассматривать позицию после конца в последовательности-результате как конец слова  
  
 `match_any` -- принимать любое сопоставление, если их возможно несколько  
  
 `match_not_null` -- не рассматривать пустую вложенную последовательность как совпадение  
  
 `match_continuous` -- не искать соответствия кроме как в начале последовательности-результата  
  
 `match_prev_avail` -- `--first` — это допустимый итератор; игнорируйте `match_not_bol` и `match_not_bow`, если они установлены  
  
 Флаги формата  
  
 `format_default` -- использовать правила формата ECMAScript  
  
 `format_sed` -- использовать правила формата sed  
  
 `format_no_copy` -- не копировать текст, который не соответствует регулярному выражению  
  
 `format_first_only` -- не искать соответствия после нахождения первого  
  
##  <a name="syntax_option_type"></a>  regex_constants::syntax_option_type  
 Флаги для выбора параметров синтаксиса.  
  
```  
enum syntax_option_type
    {    // specify RE syntax rules
    ECMAScript = 0x01,
    basic = 0x02,
    extended = 0x04,
    awk = 0x08,
    grep = 0x10,
    egrep = 0x20,
    _Gmask = 0x3F,

    icase = 0x0100,
    nosubs = 0x0200,
    optimize = 0x0400,
    collate = 0x0800
    };  
```  
  
### <a name="remarks"></a>Примечания  
 Тип — это тип битовой маски, описывающий описатели языка и модификаторы синтаксиса, используемые при компиляции регулярного выражения. Параметры можно использовать вместе с `|`. Одновременно можно использовать только один описатель языка.  
  
 Описатели языка включают:  
  
 `ECMAScript` -- компилировать как ECMAScript  
  
 `basic` -- компилировать как BRE  
  
 `extended` -- компилировать как ERE  
  
 `awk` -- компилировать как awk  
  
 `grep` -- компилировать как grep  
  
 `egrep` -- компилировать как egrep  
  
 Модификаторы синтаксиса включают:  
  
 `icase` -- не учитывать регистр при сопоставлении  
  
 `nosubs` -- реализация не должна отслеживать содержимое групп записи  
  
 `optimize` -- реализация должна отдавать приоритет скорости сопоставления, а не скорости компиляции регулярных выражений  
  
 `collate` -- учитывать регистр при сопоставлении  
  
## <a name="see-also"></a>См. также  
[\<regex>](../standard-library/regex.md)  
[Класс regex_error](../standard-library/regex-error-class.md)  
[Функции \<regex>](../standard-library/regex-functions.md)  
[Класс regex_iterator](../standard-library/regex-iterator-class.md)  
[Операторы \<regex>](../standard-library/regex-operators.md)  
[Класс regex_token_iterator](../standard-library/regex-token-iterator-class.md)  
[Класс regex_traits](../standard-library/regex-traits-class.md)  
[Определения типов \<regex>](../standard-library/regex-typedefs.md)  

