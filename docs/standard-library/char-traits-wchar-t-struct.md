---
title: "Структура char_traits&lt;wchar_t&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.char_traits<wchar_t>"
  - "char_traits<wchar_t>"
  - "string/std::char_traits<wchar_t>"
  - "std::char_traits<wchar_t>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "char_traits<wchar_t> - класс"
ms.assetid: 31f34072-04d6-4871-88fe-48e17d473484
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# Структура char_traits&lt;wchar_t&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс, специализация шаблона структуры **char\_traits\<CharType\>** с элементом типа `wchar_t`.  
  
## Синтаксис  
  
```  
template<> struct char_traits<wchar_t>;  
```  
  
## Заметки  
 Специализация позволяет структура для использования функций библиотеки, управляющих объектов этого типа `wchar_t`.  
  
## Требования  
 **Заголовок:**\<string\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Структура char\_traits](../standard-library/char-traits-struct.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)