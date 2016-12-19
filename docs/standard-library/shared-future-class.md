---
title: "Класс shared_future | Microsoft Docs"
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
  - "future/std::shared_future"
dev_langs: 
  - "C++"
ms.assetid: 454ebedd-f42b-405f-99a5-a25cc9ad7c90
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс shared_future
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Описывает *возвращает асинхронное возражает*.  В отличие от объекта [возможные](../standard-library/future-class.md), *асинхронный поставщик* можно связать с любым числом объектов `shared_future`.  
  
## Синтаксис  
  
```  
template<class Ty>  
class shared_future;  
```  
  
## Заметки  
 Не следует вызывать другие методы, отличных от `valid`, `operator=` и деструктора объекта `shared_future`, *пуст*.  
  
 объекты `shared_future` не синхронизированы.  Вызов методов в этом объекте из нескольких потоков вставляет гонку базу данных, которая содержит непредвиденные результаты.  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор shared\_future::shared\_future](../Topic/shared_future::shared_future%20Constructor.md)|Создает объект `shared_future`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод shared\_future::get](../Topic/shared_future::get%20Method.md)|Извлекает результат, который хранится в *асинхронное состояние.*|  
|[Метод shared\_future::valid](../Topic/shared_future::valid%20Method.md)|Определяет, является ли объект не пуст.|  
|[Метод shared\_future::wait](../Topic/shared_future::wait%20Method.md)|Блокирует текущий поток до тех пор, пока связанных асинхронное состояние не будет готово.|  
|[Метод shared\_future::wait\_for](../Topic/shared_future::wait_for%20Method.md)|Блоки связанного асинхронного состояния до тех пор, пока не будут готовы указанного времени или до тех пор, пока не будет истекать.|  
|[Метод shared\_future::wait\_until](../Topic/shared_future::wait_until%20Method.md)|Блоки связанного асинхронного состояния до тех пор, пока не будут готовы или до определенного момента времени.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор shared\_future::operator\=](../Topic/shared_future::operator=%20Operator.md)|Присвоить новое связанных асинхронное состояние.|  
  
## Требования  
 **Заголовок:** future  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<future\>](../standard-library/future.md)