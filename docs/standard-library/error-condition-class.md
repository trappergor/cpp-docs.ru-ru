---
title: "Класс error_condition | Microsoft Docs"
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
  - "system_error/std::error_condition"
  - "std::error_condition"
  - "error_condition"
  - "std.error_condition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "error_condition - класс"
ms.assetid: 6690f481-97c9-4554-a0ff-851dc96b7a06
caps.latest.revision: 16
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс error_condition
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет определяемые пользователем коды ошибок.  
  
## Синтаксис  
  
```  
class error_condition;  
```  
  
## Заметки  
 Объект типа `error_condition` хранит код ошибки и значение указателя на объект [категория](../standard-library/error-category-class.md), представляющий кодов ошибок, используемых для сообщенных определяемых пользователем ошибок.  
  
### конструкторов;  
  
|||  
|-|-|  
|[error\_condition](../Topic/error_condition::error_condition.md)|Создает объект типа `error_condition`.|  
  
### Определения типов  
  
|||  
|-|-|  
|[value\_type](../Topic/error_condition::value_type.md)|Тип, представляющий сохраненный код ошибки значение.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[assign](../Topic/error_condition::assign.md)|Код ошибки и присвоить значение категорию в критериям ошибки.|  
|[категория](../Topic/error_condition::category.md)|Возвращает категорию ошибки.|  
|[clear](../Topic/error_condition::clear.md)|Удаляет код ошибки и значение категорию.|  
|[сообщение](../Topic/error_condition::message.md)|Возвращает имя кода ошибки.|  
  
### Операторы  
  
|||  
|-|-|  
|[operator\=\=](../Topic/error_condition::operator==.md)|Тесты на равенство между объектами `error_condition`.|  
|[operator\!\=](../Topic/error_condition::operator!=.md)|Тесты для неравенства между объектами `error_condition`.|  
|[operator\<](../Topic/error_condition::operator%3C.md)|Тесты, если объект `error_condition`, чем объект `error_code`, используются для сравнения.|  
|[operator\=](../Topic/error_condition::operator=.md)|Присвоить новое значение перечисления в объект `error_condition`.|  
|[operator bool](../Topic/error_condition::operator%20bool.md)|Приводит к переменной типа `error_condition`.|  
  
## Требования  
 **Заголовок:**\<system\_error\>  
  
 **Пространство имен:** std  
  
## См. также  
 [Класс error\_category](../standard-library/error-category-class.md)   
 [\<system\_error\>](../standard-library/system-error.md)