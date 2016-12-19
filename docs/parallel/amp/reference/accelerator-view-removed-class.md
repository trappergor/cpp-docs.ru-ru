---
title: "Класс accelerator_view_removed | Microsoft Docs"
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
  - "amprt/Concurrency::accelerator_view_removed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс amprt/Concurrency::accelerator_view_removed"
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
caps.latest.revision: 6
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс accelerator_view_removed
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Исключение, вызываемое при сбое основного вызова DirectX из\-за механизм Windows обнаружения и восстановления времени ожидания.  
  
## Синтаксис  
  
```  
class accelerator_view_removed : public runtime_exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор accelerator\_view\_removed::accelerator\_view\_removed](../Topic/accelerator_view_removed::accelerator_view_removed%20Constructor.md)|Инициализирует новый экземпляр класса `accelerator_view_removed`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод accelerator\_view\_removed::get\_view\_removed\_reason](../Topic/accelerator_view_removed::get_view_removed_reason%20Method.md)|Возвращает код ошибки HRESULT, указывающий причину удаления объекта `accelerator_view`.|  
  
## Иерархия наследования  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен:** Concurrency  
  
## См. также  
 [Пространство имен Concurrency \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)