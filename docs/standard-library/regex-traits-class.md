---
title: "Класс regex_traits | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "regex_traits"
  - "std::tr1::regex_traits"
  - "std.tr1.regex_traits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс regex_traits [TR1]"
ms.assetid: bc5a5eed-32fc-4eb7-913d-71c42e729e81
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс regex_traits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает характеристики элементов для сопоставления.  
  
## Синтаксис  
  
```  
template<class Elem>  
    struct regex_traits {  
    regex_traits();  
  
    static size_type length(const char_type *str);  
    char_type translate(char_type ch) const;  
    char_type translate_nocase(char_type ch) const;  
    template<class FwdIt>  
        string_type transform(FwdIt first, FwdIt last) const;  
    template<class FwdIt>  
        string_type transform_primary(FwdIt first, FwdIt last) const;  
    template<class FwdIt>  
        char_class_type lookup_classname(FwdIt first, FwdIt last) const;  
    template<class FwdIt>  
        string_type lookup_collatename(FwdIt first, FwdIt last) const;  
    bool isctype(char_type ch, char_class_type cls) const;  
    int value(Elem ch, int base) const;  
    locale_type imbue(locale_type loc);  
    locale_type getloc() const;  
  
    typedef Elem char_type;  
    typedef T6 size_type;  
    typedef basic_string<Elem> string_type;  
    typedef T7 locale_type;  
    typedef T8 char_class_type;  
    };  
```  
  
#### Параметры  
 `Elem`  
 Тип элемента для описания.  
  
## Заметки  
 Класс шаблона описывает различные характеристики регулярного выражения для типа `Elem`. Класс шаблона [Класс basic\_regex](../Topic/basic_regex%20Class.md) использует эти сведения для управления элементами типа `Elem`.  
  
 Каждый объект `regex_traits` содержит объект типа `regex_traits::locale`, используемый некоторыми из его функций\-членов. Языковой стандарт по умолчанию является копией `regex_traits::locale()`. Функция\-член `imbue` заменяет объект языкового стандарта, а функция\-член `getloc` возвращает копию объекта языкового стандарта.  
  
## Требования  
 **Заголовок:** \<regex\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_traits](../standard-library/regex-traits-class.md)   
 [regex\_traits \< char \> класса](../standard-library/regex-traits-char-class.md)   
 [Класс regex\_traits\<wchar\_t\>](../standard-library/regex-traits-wchar-t-class.md)