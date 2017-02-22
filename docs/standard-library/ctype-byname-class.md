---
title: "Класс ctype_byname | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "xlocale/std::ctype_byname"
  - "std::ctype_byname"
  - "ctype_byname"
  - "std.ctype_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ctype_byname - класс"
ms.assetid: a5cec021-a1f8-425f-8757-08e6f064b604
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Класс ctype_byname
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Производный класс шаблона описание объекта, который можно использовать как аспект ctype данного языкового стандарта, включая классификацию символов и преобразование символов между ветвь и размещения и определенным языковым стандартом кодировок.  
  
## Синтаксис  
  
```  
template<class _Elem>  
class ctype_byname : public ctype<_Elem>  
{  
public:  
    explicit ctype_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit ctype_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );  
protected:  
    virtual __CLR_OR_THIS_CALL ~ctype_byname();  
};  
```  
  
## Заметки  
 Его расширение функциональности именованным определяется языковым стандартом `_Locname`.  Каждый конструктор инициализирует его базовый объект с помощью [ctype](../standard-library/ctype-class.md)\<CharType\>\(`_Refs`\) или эквивалент базового класса `ctype<char>`.  
  
## Требования  
 **Заголовок:**\<locale\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)