---
title: "Класс unsupported_feature | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::unsupported_feature"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unsupported_feature - класс"
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Класс unsupported_feature
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Исключение, вызываемое в том случае, если используется неподдерживаемая функция.  
  
## Синтаксис  
  
```  
class unsupported_feature : public runtime_exception;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор unsupported\_feature::unsupported\_feature](../Topic/unsupported_feature::unsupported_feature%20Constructor.md)|Создает новый экземпляр исключения `unsupported_feature`.|  
  
## Иерархия наследования  
 `exception`  
  
 `runtime_exception`  
  
 `unsupported_feature`  
  
## Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен:** Concurrency  
  
## См. также  
 [Пространство имен Concurrency \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)