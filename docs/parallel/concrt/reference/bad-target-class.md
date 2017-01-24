---
title: "Класс bad_target | Microsoft Docs"
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
  - "concrt/concurrency::bad_target"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_target - класс"
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс bad_target
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, которое выдается, когда блок обмена сообщениями получает указатель на целевой объект, который неверен для выполняемой операции.  
  
## Синтаксис  
  
```  
class bad_target : public std::exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор bad\_target::bad\_target](../Topic/bad_target::bad_target%20Constructor.md)|Перегружен.  Создает объект `bad_target`.|  
  
## Заметки  
 Это исключение обычно вызывается по таким причинам, как целевой объект попытается потреблять сообщения, которое зарезервировано для другой целевой объект или освобождение резервирование, которое он не имеет.  
  
## Иерархия наследования  
 `exception`  
  
 `bad_target`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md)