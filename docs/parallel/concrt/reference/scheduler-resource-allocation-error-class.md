---
title: "Класс scheduler_resource_allocation_error | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::scheduler_resource_allocation_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "scheduler_resource_allocation_error - класс"
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс scheduler_resource_allocation_error
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, возникающее из\-за ошибки получить критический ресурс в среде выполнения параллелизма.  
  
## Синтаксис  
  
```  
class scheduler_resource_allocation_error : public std::exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор scheduler\_resource\_allocation\_error::scheduler\_resource\_allocation\_error](../Topic/scheduler_resource_allocation_error::scheduler_resource_allocation_error%20Constructor.md)|Перегружен.  Создает объект `scheduler_resource_allocation_error`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод scheduler\_resource\_allocation\_error::get\_error\_code](../Topic/scheduler_resource_allocation_error::get_error_code%20Method.md)|Возвращает код ошибки, вызвавшей исключение.|  
  
## Заметки  
 Это исключение обычно возникает при сбое вызова к операционной системе из среды  выполнения параллелизма.  Код ошибки, который обычно будут возвращены из вызова метода Win32 `GetLastError` преобразуется в значение типа `HRESULT` и могут быть получены посредством метода `get_error_code`.  
  
## Иерархия наследования  
 `exception`  
  
 `scheduler_resource_allocation_error`  
  
## Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
## См. также  
 [Пространство имен concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)