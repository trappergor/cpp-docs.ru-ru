---
title: "Класс future | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "future/std::future"
dev_langs: 
  - "C++"
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Класс future
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает *возвращает асинхронное возражает*.  
  
## Синтаксис  
  
```  
template<class Ty>  
class future;  
```  
  
## Заметки  
 Каждое стандартное *асинхронный поставщик* возвращает объект, тип которого создание этого шаблона.  Объект `future` предоставляет доступ только к асинхронному поставщика, который связан с.  Если требуются несколько асинхронных возвращают объекты, которые связаны с тем же асинхронные поставщиком, скопируйте объект `future` в объект [shared\_future](../standard-library/shared-future-class.md).  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор future::future](../Topic/future::future%20Constructor.md)|Создает объект `future`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод future::get](../Topic/future::get%20Method.md)|Извлекает результат, хранящийся в асинхронном связанном состоянии.|  
|[Метод future::share](../Topic/future::share%20Method.md)|Преобразует объект в `shared_future`.|  
|[Метод future::valid](../Topic/future::valid%20Method.md)|Определяет, является ли объект не пуст.|  
|[Метод future::wait](../Topic/future::wait%20Method.md)|Блокирует текущий поток до тех пор, пока связанных асинхронное состояние не будет готово.|  
|[Метод future::wait\_for](../Topic/future::wait_for%20Method.md)|Блоки связанного асинхронного состояния до тех пор, пока не будут готовы указанного времени или до тех пор, пока не будет истекать.|  
|[Метод future::wait\_until](../Topic/future::wait_until%20Method.md)|Блоки связанного асинхронного состояния до тех пор, пока не будут готовы или до определенного момента времени.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор future::operator\=](../Topic/future::operator=%20Operator.md)|Перемещает связанных асинхронное состояние из указанного объекта.|  
  
## Требования  
 **Заголовок:** future  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)