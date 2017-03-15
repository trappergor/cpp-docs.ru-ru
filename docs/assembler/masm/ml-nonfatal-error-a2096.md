---
title: "ML Nonfatal Error A2096 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2096"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2096"
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2096
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**сегмент, группа или ожидаемый регистр сегмента**  
  
 Ожидается, но не были найдены сегмент или группа.  
  
 Одно из произойденного следующих действий:  
  
-   Левый операнд, указанный с помощью оператора переопределения сегмента \(.\) не были регистр сегмента \(CS, DS, SS, ES, fs или GS\), имя группы, имя сегмента или выражение сегмента.  
  
-   [TAKE](../../assembler/masm/assume.md) директиве дала регистр сегмента без допустимого адресов сегмента, регистр сегмента, группа или специальные  **Плоский** группы.  
  
## См. также  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)