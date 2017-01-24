---
title: "Класс regex_iterator | Microsoft Docs"
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
  - "std::tr1::regex_iterator"
  - "std.tr1.regex_iterator"
  - "regex_iterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс regex_iterator [TR1]"
ms.assetid: 0cfd8fd0-5a95-4f3c-bf8e-6ef028c423d3
caps.latest.revision: 16
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс regex_iterator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс итератора для соответствий.  
  
## Синтаксис  
  
```  
template<class BidIt, class Elem = iterator_traits<BidIt>::value_type,  
    class RXtraits = regex_traits<Elem> >  
        class regex_iterator {  
public:  
    typedef basic_regex<Elem, RXtraits> regex_type;  
    typedef match_results<BidIt> value_type;  
    typedef std::forward_iterator_tag iterator_category;  
    typedef std::ptrdiff_t difference_type;  
    typedef const match_results<BidIt>* pointer;  
    typedef const match_results<BidIt>& reference;  
  
    regex_iterator();  
    regex_iterator(BidIt first, BidIt last,  
        const regex_type& re,  
        regex_constants::match_flag_type f = regex_constants::match_default);  
  
    bool operator==(const regex_iterator& right);  
    bool operator!=(const regex_iterator& right);  
    const match_results<BidIt>& operator*();  
    const match_results<BidIt> *operator->();  
    regex_iterator& operator++();  
    regex_iterator& operator++(int);  
  
    BidIt begin;                            // exposition only  
    BidIt end;                              // exposition only  
    regex_type *pregex;                     // exposition only  
    regex_constants::match_flag_type flags; // exposition only  
    match_results<BidIt> match;             // exposition only  
    };  
```  
  
#### Параметры  
 `BidIt`  
 Тип итератора для подстрок соответствия.  
  
 `Elem`  
 Тип элементов для обеспечения соответствия.  
  
 `RXtraits`  
 Класс характеристик для элементов.  
  
## Заметки  
 Класс шаблона описывает объект постоянного прямого итератора. Он извлекает объекты типа `match_results<BidIt>`, несколько раз применяя объект регулярного выражения `*pregex` к последовательности символов, определенной диапазоном итератора `[begin, end)`.  
  
## Примеры  
 Примеры регулярных выражений см. в следующих разделах:  
  
-   [Функция regex\_match](../Topic/regex_match%20Function.md)  
  
-   [Функция regex\_replace](../Topic/regex_replace%20Function.md)  
  
-   [Функция regex\_search](../Topic/regex_search%20Function.md)  
  
-   [Функция swap](../Topic/swap%20Function%20%3Cregex%3E.md)  
  
## Требования  
 **Заголовок:** \<regex\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_iterator](../standard-library/regex-iterator-class.md)