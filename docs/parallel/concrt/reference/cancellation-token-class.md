---
title: "Класс cancellation_token | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pplcancellation_token/concurrency::cancellation_token"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token - класс"
ms.assetid: 2787df2b-e9d3-440e-bfd0-841a46a9835f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Класс cancellation_token
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `cancellation_token` представляет возможность определить, получала ли некоторая операция запрос на отмену.  Заданный токен можно связать с `task_group`, `structured_task_group` или `task` для предоставления неявной отмены.  Его также можно опрашивать на предмет отмены или зарегистрировать обратный вызов для той ситуации, когда отменяется связанный `cancellation_token_source`.  
  
## Синтаксис  
  
```  
class cancellation_token;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор cancellation\_token::cancellation\_token](../Topic/cancellation_token::cancellation_token%20Constructor.md)||  
|[Деструктор cancellation\_token::~cancellation\_token](../Topic/cancellation_token::~cancellation_token%20Destructor.md)||  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод cancellation\_token::deregister\_callback](../Topic/cancellation_token::deregister_callback%20Method.md)|Удаляет обратный вызов, ранее зарегистрированный с помощью метода `register` на основании объекта `cancellation_token_registration`, возвращенного во время регистрации.|  
|[Метод cancellation\_token::is\_cancelable](../Topic/cancellation_token::is_cancelable%20Method.md)|Возвращает значение, указывающее, может ли этот токен быть отменен или нет.|  
|[Метод cancellation\_token::is\_canceled](../Topic/cancellation_token::is_canceled%20Method.md)|Возвращает `true`, если токен был отменен.|  
|[Метод cancellation\_token::none](../Topic/cancellation_token::none%20Method.md)|Возвращает токен отмены, который никогда не может подвергаться отмене.|  
|[Метод cancellation\_token::register\_callback](../Topic/cancellation_token::register_callback%20Method.md)|Регистрирует функцию обратного вызова в токене.  Если и когда токен отменяется, выполняется обратный вызов.  Обратите внимание, что если токен уже отменен в той точке, где вызывается этот метод, обратный вызов будет выполнен немедленно и синхронно.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор cancellation\_token::operator\!\=](../Topic/cancellation_token::operator!=%20Operator.md)||  
|[Оператор cancellation\_token::operator\=](../Topic/cancellation_token::operator=%20Operator.md)||  
|[Оператор cancellation\_token::operator\=\=](../Topic/cancellation_token::operator==%20Operator.md)||  
  
## Иерархия наследования  
 `cancellation_token`  
  
## Требования  
 **Заголовок:**  pplcancellation\_token.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)