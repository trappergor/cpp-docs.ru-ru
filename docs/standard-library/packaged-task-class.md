---
title: "Класс packaged_task | Microsoft Docs"
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
  - "future/std::packaged_task"
dev_langs: 
  - "C++"
ms.assetid: 0a72cbe3-f22a-4bfe-8e50-dcb268c98780
caps.latest.revision: 9
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс packaged_task
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает *асинхронный поставщик*, программа\-оболочка вызова, сигнатура вызова `Ty(ArgTypes...)`.  Его можно вызвать его *асинхронное состояние.* содержит копию объекта помимо потенциальному результату.  
  
## Синтаксис  
  
```  
template<class>  
class packaged_task;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор packaged\_task::packaged\_task](../Topic/packaged_task::packaged_task%20Constructor.md)|Создает объект `packaged_task`.|  
|[Деструктор packaged\_task::~packaged\_task](../Topic/packaged_task::~packaged_task%20Destructor.md)|Удаляет объект `packaged_task`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод packaged\_task::get\_future](../Topic/packaged_task::get_future%20Method.md)|Возвращает объект [возможные](../standard-library/future-class.md), который имеет то же связанных асинхронное состояние.|  
|[Метод packaged\_task::make\_ready\_at\_thread\_exit](../Topic/packaged_task::make_ready_at_thread_exit%20Method.md)|Вызывает можно вызвать объект, хранящийся в асинхронном неделимым блоком, связанном состоянии и сохраняет возвращаемое значение.|  
|[Метод packaged\_task::reset](../Topic/packaged_task::reset%20Method.md)|Заменяет связанный асинхронное состояние.|  
|[Метод packaged\_task::swap](../Topic/packaged_task::swap%20Method.md)|Меняет местами асинхронное состояние, связанное с этим из указанного объекта.|  
|[Метод packaged\_task::valid](../Topic/packaged_task::valid%20Method.md)|Указывает, имеет ли объект связанных асинхронное состояние.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор packaged\_task::operator\=](../Topic/packaged_task::operator=%20Operator.md)|Перемещает связанных асинхронное состояние из указанного объекта.|  
|[Оператор packaged\_task::operator\(\)](../Topic/packaged_task::operator\(\)%20Operator.md)|Вызывает можно вызвать объект, хранящийся в асинхронном связанном состоянии, неделимым блоком, сохраняет возвращаемое значение, и устанавливает состояние *для подготовки*.|  
|[Оператор packaged\_task::operator bool](../Topic/packaged_task::operator%20bool%20Operator.md)|Указывает, имеет ли объект связанных асинхронное состояние.|  
  
## Требования  
 **Заголовок:** future  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)