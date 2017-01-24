---
title: "Класс error_code | Microsoft Docs"
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
  - "error_code"
  - "std.error_code"
  - "std::error_code"
  - "system_error/std::error_code"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error_code - класс"
ms.assetid: c09b4a96-cb14-4281-a319-63543f9b2b4a
caps.latest.revision: 17
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс error_code
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет низкоуровневые системные ошибки, предоставления с.  
  
## Синтаксис  
  
```  
class error_code;  
```  
  
## Заметки  
 Объект класса `error_code` типа хранит код ошибки и значение указателя на объект [категория](../standard-library/error-category-class.md), представляющий кодов ошибок, описывающие найденные низкоуровневые системные ошибки.  
  
### конструкторов;  
  
|||  
|-|-|  
|[error\_code](../Topic/error_code::error_code.md)|Создает объект типа `error_code`.|  
  
### Определения типов  
  
|||  
|-|-|  
|[value\_type](../Topic/error_code::value_type.md)|Тип, представляющий сохраненный код ошибки значение.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[assign](../Topic/error_code::assign.md)|Код ошибки и присвоить значение категорию в код ошибки.|  
|[категория](../Topic/error_code::category.md)|Возвращает категорию ошибки.|  
|[clear](../Topic/error_code::clear.md)|Удаляет код ошибки и значение категорию.|  
|[default\_error\_condition](../Topic/error_code::default_error_condition.md)|Возвращает условие ошибки по умолчанию.|  
|[сообщение](../Topic/error_code::message.md)|Возвращает имя кода ошибки.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\=\=](../Topic/error_code::operator==.md)|Тесты на равенство между объектами `error_code`.|  
|[operator\!\=](../Topic/error_code::operator!=.md)|Тесты для неравенства между объектами `error_code`.|  
|[operator\<](../Topic/error_code::operator%3C.md)|Тесты, если объект `error_code`, чем объект `error_code`, используются для сравнения.|  
|[operator\=](../Topic/error_code::operator=.md)|Присвоить новое значение перечисления в объект `error_code`.|  
|[operator bool](../Topic/error_code::operator%20bool.md)|Приводит к переменной типа `error_code`.|  
  
## Требования  
 **Заголовок:**\<system\_error\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Класс error\_category](../standard-library/error-category-class.md)   
 [\<system\_error\>](../standard-library/system-error.md)