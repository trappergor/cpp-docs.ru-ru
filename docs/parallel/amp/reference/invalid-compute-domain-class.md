---
title: "Класс invalid_compute_domain | Microsoft Docs"
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
  - "amprt/Concurrency::invalid_compute_domain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_compute_domain - класс"
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс invalid_compute_domain
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Исключение, выдаваемое в том случае, если среда выполнения не может запустить ядро с использованием домена вычислений указанного в месте вызова [parallel\_for\_each](../Topic/parallel_for_each%20Function%20\(C++%20AMP\).md).  
  
## Синтаксис  
  
```  
class invalid_compute_domain : public runtime_exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор invalid\_compute\_domain::invalid\_compute\_domain](../Topic/invalid_compute_domain::invalid_compute_domain%20Constructor.md)|Инициализирует новый экземпляр класса `invalid_compute_domain`.|  
  
## Иерархия наследования  
 `exception`  
  
 `runtime_exception`  
  
 `invalid_compute_domain`  
  
## Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен:** Concurrency  
  
## См. также  
 [Пространство имен Concurrency \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)