---
title: "Класс promise | Microsoft Docs"
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
  - "future/std::promise"
dev_langs: 
  - "C++"
ms.assetid: 2931558c-d94a-4ba1-ac4f-20bf7b6e23f9
caps.latest.revision: 15
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс promise
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает *асинхронный поставщик*.  
  
## Синтаксис  
  
```  
template<class Ty>  
class promise;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор promise::promise](../Topic/promise::promise%20Constructor.md)|Создает объект `promise`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод promise::get\_future](../Topic/promise::get_future%20Method.md)|Возвращает значение [возможные](../standard-library/future-class.md), связанных с этим обещанием.|  
|[Метод promise::set\_exception](../Topic/promise::set_exception%20Method.md)|Задает неделимым блоком, результат отображения этого обещания исключение.|  
|[Метод promise::set\_exception\_at\_thread\_exit](../Topic/promise::set_exception_at_thread_exit%20Method.md)|Задает неделимым блоком, результат отображения этого обещания исключение и доставляет уведомления локальный для потока только после того, как все объекты в текущем потоке были уничтожены \(обычно на выходе потока\).|  
|[Метод promise::set\_value](../Topic/promise::set_value%20Method.md)|Задает неделимым блоком, результат этого обещания отображения значения.|  
|[Метод promise::set\_value\_at\_thread\_exit](../Topic/promise::set_value_at_thread_exit%20Method.md)|Задает неделимым блоком, результат этого обещания отображения значения и доставляет уведомления локальный для потока только после того, как все объекты в текущем потоке были уничтожены \(обычно на выходе потока\).|  
|[Метод promise::swap](../Topic/promise::swap%20Method.md)|Меняет местами *асинхронное состояние.* этого обещания с одним из указанного объекта обещания.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор promise::operator\=](../Topic/promise::operator=%20Operator.md)|Назначение общего состояния данного объекта обещания.|  
  
## Иерархия наследования  
 `promise`  
  
## Требования  
 **Заголовок:** future  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)