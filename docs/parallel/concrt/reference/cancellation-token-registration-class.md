---
title: "Класс cancellation_token_registration | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pplcancellation_token/concurrency::cancellation_token_registration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cancellation_token_registration - класс"
ms.assetid: 823d63f4-7233-4d65-8976-6152ccf12d0e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Класс cancellation_token_registration
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Класс `cancellation_token_registration` представляет уведомление обратного вызова из `cancellation_token`.  При использовании метода `register` на `cancellation_token` для получения уведомления о времени выполнения отмены объект `cancellation_token_registration` возвращается как дескриптор для обратного вызова, чтобы вызывающий код мог запросить, чтобы определенный обратный вызов больше не выполнялся с помощью метода `deregister`.  
  
## Синтаксис  
  
```  
class cancellation_token_registration;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор cancellation\_token\_registration::cancellation\_token\_registration](../Topic/cancellation_token_registration::cancellation_token_registration%20Constructor.md)||  
|[Деструктор cancellation\_token\_registration::~cancellation\_token\_registration](../Topic/cancellation_token_registration::~cancellation_token_registration%20Destructor.md)||  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор cancellation\_token\_registration::operator\!\=](../Topic/cancellation_token_registration::operator!=%20Operator.md)||  
|[Оператор cancellation\_token\_registration::operator\=](../Topic/cancellation_token_registration::operator=%20Operator.md)||  
|[Оператор cancellation\_token\_registration::operator\=\=](../Topic/cancellation_token_registration::operator==%20Operator.md)||  
  
## Иерархия наследования  
 `cancellation_token_registration`  
  
## Требования  
 **Заголовок:**  pplcancellation\_token.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)