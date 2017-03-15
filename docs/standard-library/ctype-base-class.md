---
title: "Класс ctype_base | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "locale/std::ctype_base"
  - "std.ctype_base"
  - "ctype_base"
  - "std::ctype_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ctype_base - класс"
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс ctype_base
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Этот класс служит базовым классом для аспектов шаблона класса [ctype](../standard-library/ctype-class.md).  Базовый класс для класса ctype, используемый для определения типов перечисления, чтобы разделить на две категории: потоковые или запуска символы или по отдельности или во все диапазоны.  
  
## Синтаксис  
  
```  
struct ctype_base : public locale::facet  
{  
    enum  
    {  
        alnum, alpha, cntrl, digit, graph,  
        lower, print, punct, space, upper,  
        xdigit  
    };  
    typedef short mask;  
    ctype_base(  
        size_t _Refs = 0  
    );  
    ~ctype_base();  
};  
```  
  
## Заметки  
 Идентифицирует маску перечисления.  Каждая константа перечисления характеризует альтернативный способ разделить на две категории: потоковые символы, заданное с помощью функций с одинаковыми именами, объявленные в заголовке \<ctype.h\>.  Константы:  
  
-   функция **space** \( [isspace](../Topic/isspace.md)\)  
  
-   функция **print** \( [isprint](../Topic/isprint.md)\)  
  
-   функция **cntrl** \( [iscntrl](../Topic/iscntrl.md)\)  
  
-   функция **upper** \( [isupper](../Topic/isupper.md)\)  
  
-   функция **lower** \( [islower](../Topic/islower.md)\)  
  
-   функция **digit** \( [isdigit](../Topic/isdigit.md)\)  
  
-   функция **punct** \( [ispunct](../Topic/ispunct.md)\)  
  
-   функция **xdigit** \( [isxdigit](../Topic/isxdigit.md)\)  
  
-   функция **alpha** \( [isalpha](../Topic/isalpha.md)\)  
  
-   функция **alnum** \( [isalnum](../Topic/isalnum.md)\)  
  
-   функция **graph** \( [isgraph](../Topic/isgraph.md)\)  
  
 Можно характеризует классификации сочетания из колцеобразным уплотнением эти константы.  В частности, он всегда наоборот **alnum** \=\= \(**alpha** ``&#124; **digit**\) и **graph** \=\= \(**alnum**``&#124; **punct**\).  
  
## Требования  
 **Header:**\<locale\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)