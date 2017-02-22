---
title: "Класс unique_lock | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mutex/std::unique_lock"
dev_langs: 
  - "C++"
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Класс unique_lock
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет шаблон, можно создать для создания объектов, управляющих блокировать и разблокировать `mutex`.  
  
## Синтаксис  
  
```  
template<class Mutex>  
class unique_lock;  
```  
  
## Заметки  
 Аргумент `Mutex` шаблона должен иметь имя *тип мьютексов*.  
  
 По сути, `unique_lock` сохраняет указатель на связанный объект `mutex` и `bool`, указывающее, имеет ли текущий поток `mutex`.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Name|Описание|  
|----------|--------------|  
|`unique_lock::mutex_type`|Синоним для аргумента `Mutex` шаблона.|  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор unique\_lock::unique\_lock](../Topic/unique_lock::unique_lock%20Constructor.md)|Создает объект `unique_lock`.|  
|[Деструктор unique\_lock::~unique\_lock](../Topic/unique_lock::~unique_lock%20Destructor.md)|Выпуски все ресурсы, связанные с объектом `unique_lock`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод unique\_lock::lock](../Topic/unique_lock::lock%20Method.md)|Блокирует вызывающий поток до тех пор, пока поток не получит владельца связанного `mutex`.|  
|[Метод unique\_lock::mutex](../Topic/unique_lock::mutex%20Method.md)|Извлекает сохраненный указатель на связанный `mutex`.|  
|[Метод unique\_lock::owns\_lock](../Topic/unique_lock::owns_lock%20Method.md)|Указывает, имеет ли вызывающий поток, связанный `mutex`.|  
|[Метод unique\_lock::release](../Topic/unique_lock::release%20Method.md)|Отделяет объект `unique_lock` из связанного объекта `mutex`.|  
|[Метод unique\_lock::swap](../Topic/unique_lock::swap%20Method.md)|Замена полезные `mutex` и состояние владения с одним из указанного объекта.|  
|[Метод unique\_lock::try\_lock](../Topic/unique_lock::try_lock%20Method.md)|Попытки получить права владельца связанного объекта `mutex` без блокировки.|  
|[Метод unique\_lock::try\_lock\_for](../Topic/unique_lock::try_lock_for%20Method.md)|Попытки получить права владельца связанного объекта `mutex` без блокировки.|  
|[Метод unique\_lock::try\_lock\_until](../Topic/unique_lock::try_lock_until%20Method.md)|Попытки получить права владельца связанного объекта `mutex` без блокировки.|  
|[Метод unique\_lock::unlock](../Topic/unique_lock::unlock%20Method.md)|Владение выпусков связанного `mutex`.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор unique\_lock::operator bool](../Topic/unique_lock::operator%20bool%20Operator.md)|Указывает, имеет ли вызывающий поток владельца связанного `mutex`.|  
|[Оператор unique\_lock::operator\=](../Topic/unique_lock::operator=%20Operator.md)|Копирует, сохраняют указатель `mutex` и связывать состояние владения из указанного объекта.|  
  
## Иерархия наследования  
 `unique_lock`  
  
## Требования  
 **Заголовок:** mutex  
  
 **Пространство имен:** std  
  
## См. также  
 [Справочные материалы по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)