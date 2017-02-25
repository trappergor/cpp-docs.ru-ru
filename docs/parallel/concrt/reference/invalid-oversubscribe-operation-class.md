---
title: "Класс invalid_oversubscribe_operation | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::invalid_oversubscribe_operation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_oversubscribe_operation - класс"
ms.assetid: 0a9c5f08-d5e6-4ad0-90a9-517472b3ac28
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс invalid_oversubscribe_operation
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, возникающее при вызове метода `Context::Oversubscribe` с параметром `_BeginOversubscription`, равным `false` без предварительного вызова метода `Context::Oversubscribe` с параметром `_BeginOversubscription`, имеющим значение `true`.  
  
## Синтаксис  
  
```  
class invalid_oversubscribe_operation : public std::exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор invalid\_oversubscribe\_operation::invalid\_oversubscribe\_operation](../Topic/invalid_oversubscribe_operation::invalid_oversubscribe_operation%20Constructor.md)|Перегружен.  Создает объект `invalid_oversubscribe_operation`.|  
  
## Иерархия наследования  
 `exception`  
  
 `invalid_oversubscribe_operation`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Метод Context::Oversubscribe](../Topic/Context::Oversubscribe%20Method.md)