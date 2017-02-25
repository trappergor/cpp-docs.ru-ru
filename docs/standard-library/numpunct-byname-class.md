---
title: "Класс numpunct_byname | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.numpunct_byname"
  - "numpunct_byname"
  - "xlocnum/std::numpunct_byname"
  - "std::numpunct_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numpunct_byname - класс"
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# Класс numpunct_byname
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Производный класс шаблона описание объекта, который можно использовать как аспект `numpunct` данного языкового стандарта для числового форматирования и знаки препинания и логических выражений.  
  
## Синтаксис  
  
```  
template<Class CharType>  
    class numpunct_byname : public numpunct<Elem> {  
public:  
    explicit numpunct_byname(  
        const char* _Locname,  
        size_t _Refs = 0  
    );  
    explicit numpunct_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );  
protected:  
    virtual ~numpunct_byname( );  
   };  
```  
  
## Заметки  
 Его расширение функциональности определяется языковым стандартом `_Locname`[именованный](../Topic/locale::name.md).  Конструктор инициализирует его базовый объект с помощью [numpunct](../Topic/numpunct::numpunct.md)\<CharType\>\(`_Refs`\).  
  
## Требования  
 **Заголовок:**\<locale\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)