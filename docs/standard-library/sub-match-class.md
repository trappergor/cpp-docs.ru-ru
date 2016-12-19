---
title: "Класс sub_match | Microsoft Docs"
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
  - "sub_match"
  - "std::tr1::sub_match"
  - "std.tr1.sub_match"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс sub_match [TR1]"
ms.assetid: 804e2b9e-d16a-4c4c-ac60-024e0b2dd0e8
caps.latest.revision: 19
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс sub_match
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает подстроку соответствия.  
  
## Синтаксис  
  
```  
template<class BidIt>  
    class sub_match  
        : public std::pair<BidIt, BidIt> {  
public:  
    bool matched;  
    int compare(const sub_match& right) const;  
    int compare(const basic_string<value_type>& right) const;  
    int compare(const value_type *right) const;  
    difference_type length() const;  
    operator basic_string<value_type>() const;  
    basic_string<value_type> str() const;  
    typedef typename iterator_traits<BidIt>::value_type value_type;  
    typedef typename iterator_traits<BidIt>::difference_type difference_type;  
    typedef BidIt iterator;  
    };  
```  
  
#### Параметры  
 `BidIt`  
 Тип итератора для подстрок соответствия.  
  
## Заметки  
 Класс шаблона описывает объект, который определяет последовательность символов, соответствующих группе записи в вызове [Функция regex\_match](../Topic/regex_match%20Function.md) или [Функция regex\_search](../Topic/regex_search%20Function.md). Объекты типа [Класс match\_results](../standard-library/match-results-class.md) содержат массив таких объектов, по одному для каждой группы записи в регулярном выражении, которое использовалось при поиске.  
  
 Если группа записи не соответствует члену данных объекта, `matched` содержит значение false, а два итератора `first` и `second` \(наследуются от базового класса `std::pair`\) равны. Если обнаружено соответствие группе записи, `matched` содержит значение true, итератор `first` указывает на первый символ в целевой последовательности, которая соответствует группе записи, а итератор `second` указывает на одну позицию после последнего символа в целевой последовательности, которая соответствует группе записи. Обратите внимание, что для соответствия нулевой длины член `matched` должен содержать значение true, два итератора быть эквиваленты и оба указывать на одну позицию соответствия.  
  
 Соответствие нулевой длины может возникать, когда группа записи состоит только из утверждения или из повторения, допускающего нулевые повторы. Например:  
  
 "^" соответствует целевой последовательности "a"; объект `sub_match`, соответствующий группе записи 0, содержит два итератора, которые указывают на первый символ в последовательности.  
  
 "b\(a\*\)b" соответствует целевой последовательности "bb"; объект `sub_match`, соответствующий группе записи 1, содержит два итератора, которые указывают на второй символ в последовательности.  
  
## Требования  
 **Заголовок:** \<regex\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<regex\>](../standard-library/regex.md)   
 [sub\_match](../standard-library/sub-match-class.md)   
 [Функция regex\_match](../Topic/regex_match%20Function.md)   
 [Функция regex\_search](../Topic/regex_search%20Function.md)