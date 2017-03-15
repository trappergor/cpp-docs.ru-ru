---
title: "Класс messages_byname | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "messages_byname"
  - "std::messages_byname"
  - "std.messages_byname"
  - "xlocmes/std::messages_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "messages_byname - класс"
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# Класс messages_byname
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Производный класс шаблона описание объекта, который можно использовать как аспект сообщения заданного языкового стандарта, включая извлечения локализованных сообщений.  
  
## Синтаксис  
  
```  
template<class CharType>  
    class messages_byname : public messages<CharType> {  
public:  
    explicit messages_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit messages_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );   
protected:  
    virtual ~messages_byname();  
};  
```  
  
#### Параметры  
 `_Locname`  
 Именованный языковой стандарт.  
  
 `_Refs`  
 Начальное число ссылок.  
  
## Заметки  
 Его расширение функциональности именованным определяется языковым стандартом `_Locname`.  Каждый конструктор инициализирует его базовый объект с помощью [сообщения](../Topic/messages::messages.md)\<CharType\>\(`_Refs`\).  
  
## Требования  
 **Заголовок:**\<locale\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)