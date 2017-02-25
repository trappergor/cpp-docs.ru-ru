---
title: "CComAutoDeleteCriticalSection Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComAutoDeleteCriticalSection"
  - "CComAutoDeleteCriticalSection"
  - "ATL::CComAutoDeleteCriticalSection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAutoDeleteCriticalSection class"
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CComAutoDeleteCriticalSection Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет методы для получения объекта и освобождение владение критической секции.  
  
## Синтаксис  
  
```  
  
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection  
  
```  
  
## Заметки  
 `CComAutoDeleteCriticalSection` производный от класса [CComSafeDeleteCriticalSection](../Topic/CComSafeDeleteCriticalSection%20Class.md).  Однако `CComAutoDeleteCriticalSection` переопределяет метод [Термин](../Topic/CComSafeDeleteCriticalSection::Term.md) к доступу `private`, который обеспечивает очистку внутренней памяти, чтобы выполняться только в том случае, если экземпляры этого класса передаются из области или явно удалены из памяти.  
  
 Этот класс не добавляет никаких дополнительных методов с его базовым классом.  См. раздел [CComSafeDeleteCriticalSection](../Topic/CComSafeDeleteCriticalSection%20Class.md) и [CComCriticalSection](../Topic/CComCriticalSection%20Class.md) дополнительные сведения о вспомогательных классов критической секции.  
  
## Иерархия наследования  
 [CComCriticalSection](../Topic/CComCriticalSection%20Class.md)  
  
 [CComSafeDeleteCriticalSection](../Topic/CComSafeDeleteCriticalSection%20Class.md)  
  
 `CComAutoDeleteCriticalSection`  
  
## Требования  
 **Header:**  atlcore.h  
  
## См. также  
 [CComSafeDeleteCriticalSection Class](../Topic/CComSafeDeleteCriticalSection%20Class.md)   
 [CComCriticalSection Class](../Topic/CComCriticalSection%20Class.md)   
 [Class Overview](../../atl/atl-class-overview.md)