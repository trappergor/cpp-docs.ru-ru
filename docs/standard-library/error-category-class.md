---
title: "Класс error_category | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::error_category"
  - "system_error/std::error_category"
  - "error_category"
  - "std.error_category"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error_category - класс"
ms.assetid: e0a71e14-852d-4905-acd6-5f8ed426706d
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# Класс error_category
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет абстрактный, общий базовый класс для объектов, описывающий категорию кодов ошибок.  
  
## Синтаксис  
  
```  
class error_category;  
```  
  
## Заметки  
 Реализация двух стандартных объектов `error_category`: [generic\_category](../Topic/generic_category.md) и [system\_category](../Topic/system_category.md).  
  
### TypeDefs  
  
|||  
|-|-|  
|[value\_type](../Topic/error_category::value_type.md)|Тип, представляющий значение кода хранимых ошибки.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[default\_error\_condition](../Topic/error_category::default_error_condition.md)|Сохраняет значение кода ошибки для объекта условия ошибки.|  
|[equivalent](../Topic/error_category::equivalent.md)|Возвращает значение, указывающее, эквивалентны ли объекты ошибок.|  
|[сообщение](../Topic/error_category::message.md)|Возвращает имя указанного кода ошибки.|  
|[имя](../Topic/error_category::name.md)|Возвращает имя категории.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\=\=](../Topic/error_category::operator==.md)|Проверяет на равенство `error_category` объектов.|  
|[operator\!\=](../Topic/error_category::operator!=.md)|Проверяет на неравенство между `error_category` объектов.|  
|[operator\<](../Topic/error_category::operator%3C.md)|Проверяет, [error\_category](../standard-library/error-category-class.md) объект меньше, чем `error_category` переданный объект для сравнения.|  
  
## Требования  
 **Заголовок:** \<system\_error\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<system\_error\>](../standard-library/system-error.md)