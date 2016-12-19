---
title: "lastprivate | Microsoft Docs"
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
  - "lastprivate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lastprivate OpenMP clause"
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# lastprivate
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Указывает, что версия включающего контекста переменной задается равным закрытой версии любого поток выполняет итерацию \(последняя конструкция для\-цикла\) или последний раздел \#pragma \(partitions\).  
  
## Синтаксис  
  
```  
lastprivate(var)  
```  
  
## Заметки  
 Здесь:  
  
 `var`  
 Переменная которой установлено равным закрытой версии любого поток выполняет итерацию \(последняя конструкция для\-цикла\) или последний раздел \#pragma \(partitions\).  
  
## Заметки  
 `lastprivate` применяется к следующим рекомендациям:  
  
-   [for](../Topic/for%20\(OpenMP\).md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 Дополнительные сведения см. в разделе [2.7.2.3 lastprivate](../Topic/2.7.2.3%20lastprivate.md).  
  
## Пример  
 См. [schedule](../../../parallel/openmp/reference/schedule.md) пример использования  `lastprivate` предложение.  
  
## См. также  
 [Clauses](../../../parallel/openmp/reference/openmp-clauses.md)