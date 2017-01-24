---
title: "Класс uninitialized_object | Microsoft Docs"
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
  - "amprt/Concurrency::uninitialized_object"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "uninitialized_object - класс"
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс uninitialized_object
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Исключение, которое вызывается, когда используется неинициализированный объект.  
  
## Синтаксис  
  
```  
class uninitialized_object : public runtime_exception;  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор uninitialized\_object::uninitialized\_object](../Topic/uninitialized_object::uninitialized_object%20Constructor.md)|Инициализирует новый экземпляр класса `uninitialized_object`.|  
  
## Иерархия наследования  
 `exception`  
  
 `runtime_exception`  
  
 `uninitialized_object`  
  
## Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен:** Concurrency  
  
## См. также  
 [Пространство имен Concurrency \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)