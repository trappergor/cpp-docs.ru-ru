---
title: "Класс critical_section | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::critical_section"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "critical_section - класс"
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# Класс critical_section
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Не реентрабельный мьютекс, который учитывает явным образом среду параллелизма.  
  
## Синтаксис  
  
```  
class critical_section;  
```  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`native_handle_type`|Ссылка на объект `critical_section`.|  
  
### Общие классы  
  
|Имя|Описание|  
|---------|--------------|  
|[Класс critical\_section::scoped\_lock](../Topic/critical_section::scoped_lock%20Class.md)|Безопасная в отношении исключений оболочка RAII для объекта `critical_section`.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор critical\_section::critical\_section](../Topic/critical_section::critical_section%20Constructor.md)|Создает новый критический раздел.|  
|[Деструктор critical\_section::~critical\_section](../Topic/critical_section::~critical_section%20Destructor.md)|Уничтожает критический раздел.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод critical\_section::lock](../Topic/critical_section::lock%20Method.md)|Получает данную критическую секцию.|  
|[Метод critical\_section::native\_handle](../Topic/critical_section::native_handle%20Method.md)|Возвращает собственный дескриптор для данной платформы, если таковой существует.|  
|[Метод critical\_section::try\_lock](../Topic/critical_section::try_lock%20Method.md)|Пытается получить блокировку без блокировки.|  
|[Метод critical\_section::try\_lock\_for](../Topic/critical_section::try_lock_for%20Method.md)|Пытается получить блокировку без блокировки указанное число миллисекунд.|  
|[Метод critical\_section::unlock](../Topic/critical_section::unlock%20Method.md)|Снимает блокировку критической секции.|  
  
## Заметки  
 Для получения дополнительной информации см. [Структуры данных синхронизации](../Topic/Synchronization%20Data%20Structures.md).  
  
## Иерархия наследования  
 `critical_section`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс reader\_writer\_lock](../Topic/reader_writer_lock%20Class.md)