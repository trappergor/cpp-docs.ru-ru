---
title: "Класс invalid_link_target | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::invalid_link_target"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_link_target - класс"
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс invalid_link_target
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, которое создается, когда вызывается метод `link_target` блока обмена сообщениями и блок и не может создать связь с целевым объектом.  Это может быть результатом превышения числа ссылок, допустимых для блока сообщений, или попытки связать указанную цель с одним и тем же источником дважды.  
  
## Синтаксис  
  
```  
class invalid_link_target : public std::exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор invalid\_link\_target::invalid\_link\_target](../Topic/invalid_link_target::invalid_link_target%20Constructor.md)|Перегружен.  Создает объект `invalid_link_target`.|  
  
## Иерархия наследования  
 `exception`  
  
 `invalid_link_target`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md)