---
title: "Ошибка компилятора C3204 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3204"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3204"
ms.assetid: 06e578da-0262-48c8-b2ae-be1cd6d28884
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3204
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

нельзя вызвать "\_alloca" в пределах блока catch  
  
 Эта ошибка возникает при использовании вызова [\_alloca](../../c-runtime-library/reference/alloca.md) из блока catch.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3204:  
  
```  
// C3204.cpp // compile with: /EHsc #include <malloc.h> void ShowError(void) { try { } catch(...) { _alloca(1);   // C3204 } }  
```