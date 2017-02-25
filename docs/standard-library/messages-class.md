---
title: "Класс messages | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "messages"
  - "xlocmes/std::messages"
  - "std.messages"
  - "std::messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "messages - класс"
ms.assetid: c4c71f40-4f24-48ab-9f7c-daccd8d5bd83
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# Класс messages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Класс шаблона, описывающий объект, который можно использовать в качестве аспекта языкового стандарта для извлечения локализованных сообщений из каталога интернационализированных сообщений для заданного языкового стандарта.  
  
 В настоящее время при использовании данного класса сообщений сообщения не создаются.  
  
## Синтаксис  
  
```  
template <class CharType>  
   class messages : public messages_base;  
```  
  
#### Параметры  
 `CharType`  
 Тип, используемый внутри программы для кодирования символов в языковом стандарте.  
  
## Заметки  
 Как и в случае любого другого аспекта языкового стандарта, начальное сохраненное значение статического идентификатора объекта равно нулю. Первая попытка получить доступ к сохраненному значению сохранит уникальное положительное значение в **идентификатор**  
  
 По сути, этот аспект открывает каталог сообщений, заданных в базовом классе messages\_base, извлекает необходимую информацию и закрывает каталог.  
  
### Конструкторы  
  
|||  
|-|-|  
|[сообщения](../Topic/messages::messages.md)|Функция конструктора аспекта сообщения.|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/messages::char_type.md)|Тип символа, используемого для отображения сообщений.|  
|[string\_type](../Topic/messages::string_type.md)|Тип, описывающий строку типа `basic_string`, содержащую символы типа `CharType`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[закрыть](../Topic/messages::close.md)|Закрывает каталог сообщений.|  
|[do\_close](../Topic/messages::do_close.md)|Виртуальная функция, вызываемая для закрытия каталога сообщений.|  
|[do\_get](../Topic/messages::do_get.md)|Виртуальная функция, вызываемая для извлечения каталога сообщений.|  
|[do\_open](../Topic/messages::do_open.md)|Виртуальная функция, вызываемая для открытия каталога сообщений.|  
|[get](../Topic/messages::get.md)|Извлекает каталог сообщений.|  
|[open](../Topic/messages::open.md)|Открывает каталог сообщений.|  
  
## Требования  
 **Заголовок:** \<locale\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<locale\>](../standard-library/locale.md)   
 [Класс messages\_base](../Topic/messages_base%20Class.md)   
 [Потокобезопасность в стандартной библиотеке C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)