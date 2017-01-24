---
title: "Класс time_put_byname | Microsoft Docs"
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
  - "time_put_byname"
  - "xloctime/std::time_put_byname"
  - "std.time_put_byname"
  - "std::time_put_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_put_byname - класс"
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
caps.latest.revision: 25
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс time_put_byname
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Производный класс шаблона описывает объект, который можно использовать как аспект языкового стандарта типа `time_put`\< CharType, OutputIterator \>.  
  
## Синтаксис  
  
```  
template<class CharType,  
 class OutIt = ostreambuf_iterator<CharType, char_traits<CharType> > >  
 class time_put_byname : public time_put<CharType, OutputIterator>  
{  
public:  
    explicit time_put_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit time_put_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );  
protected:  
    virtual ~time_put_byname();  
};  
```  
  
#### Параметры  
 `_Locname`  
 Имя языкового стандарта.  
  
 `_Refs`  
 Начальное значение счетчика ссылок.  
  
## Заметки  
 Его поведение определяется [с именем](../Topic/locale::name.md) языкового стандарта `_Locname`. Каждый конструктор инициализирует свой базовый объект с [time\_put](../Topic/time_put::time_put.md)\< CharType, OutputIterator \> \(`_Refs`\).  
  
## Требования  
 **Заголовок:** \<locale\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)