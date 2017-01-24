---
title: "Класс regex_error | Microsoft Docs"
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
  - "std::tr1::regex_error"
  - "regex_error"
  - "std.tr1.regex_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс regex_error [TR1]"
ms.assetid: 3333a1a3-ca6f-4612-84b2-1b4c7e3db5a4
caps.latest.revision: 19
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс regex_error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Сообщает о неверном объекте basic\_regex.  
  
## Синтаксис  
  
```  
class regex_error  
    : public std::runtime_error {  
public:  
    explicit regex_error(regex_constants::error_code error);  
    regex_constants::error_code code() const;  
    };  
```  
  
## Заметки  
 Класс описывает объект исключения, создаваемый для уведомления об ошибке в построении или использовании объекта `basic_regex`.  
  
## Требования  
 **Заголовок:** \<regex\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<regex\>](../standard-library/regex.md)   
 [regex\_error](../standard-library/regex-error-class.md)