---
title: "Класс cancellation_token_source | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pplcancellation_token/concurrency::cancellation_token_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token_source - класс"
ms.assetid: 3548b1a0-12b0-4334-95db-4bf57141c066
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Класс cancellation_token_source
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `cancellation_token_source` представляет возможность отмены некоторой отменяемой операции.  
  
## Синтаксис  
  
```  
class cancellation_token_source;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор cancellation\_token\_source::cancellation\_token\_source](../Topic/cancellation_token_source::cancellation_token_source%20Constructor.md)|Перегружен.  Создает новый `cancellation_token_source`.  Источник можно использовать, чтобы сигнализировать об отмене некоторой отменяемой операции.|  
|[Деструктор cancellation\_token\_source::~cancellation\_token\_source](../Topic/cancellation_token_source::~cancellation_token_source%20Destructor.md)||  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод cancellation\_token\_source::cancel](../Topic/cancellation_token_source::cancel%20Method.md)|Отменяет токен.  Любой элемент `task_group`, `structured_task_group` или `task`, который использует этот токен, будет отменен при этом вызове и создаст исключение в следующей точке прерывания.|  
|[Метод cancellation\_token\_source::create\_linked\_source](../Topic/cancellation_token_source::create_linked_source%20Method.md)|Перегружен.  Создает `cancellation_token_source`, который отменяется при отмене предоставленного токена.|  
|[Метод cancellation\_token\_source::get\_token](../Topic/cancellation_token_source::get_token%20Method.md)|Возвращает токен отмены, связанный с данным источником.  Возвращенный токен можно опрашивать на предмет отмены или предоставить обратный вызов, если и когда произойдет отмена.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор cancellation\_token\_source::operator\!\=](../Topic/cancellation_token_source::operator!=%20Operator.md)||  
|[Оператор cancellation\_token\_source::operator\=](../Topic/cancellation_token_source::operator=%20Operator.md)||  
|[Оператор cancellation\_token\_source::operator\=\=](../Topic/cancellation_token_source::operator==%20Operator.md)||  
  
## Иерархия наследования  
 `cancellation_token_source`  
  
## Требования  
 **Заголовок:**  pplcancellation\_token.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)