---
title: "Структура char_traits&lt;char16_t&gt; | Microsoft Docs"
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
  - "std::char_traits<char16_t>"
  - "std.char_traits<char16_t>"
  - "char_traits<char16_t>"
  - "string/std::char_traits<char16_t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<char16_t> - класс"
ms.assetid: 5daf3b62-dd6e-451f-b189-0350a04ff966
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Структура char_traits&lt;char16_t&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Структура, которая специализация шаблона структуры **char\_traits\<CharType\>** с элементом типа `char16_t`.  
  
## Синтаксис  
  
```  
template<> struct char_traits<char16_t>;  
```  
  
## Заметки  
 Специализация позволяет структура для использования функций библиотеки, управляющих объектов типа `char16_t`.  
  
## Требования  
 **Заголовок:**\<string\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<string\>](../standard-library/string.md)   
 [Структура char\_traits](../standard-library/char-traits-struct.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)