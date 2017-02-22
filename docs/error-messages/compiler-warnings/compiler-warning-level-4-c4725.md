---
title: "Предупреждение компилятора (уровень 4) C4725 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4725"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4725"
ms.assetid: effa0335-71c3-4b3b-8618-da4b9b46a95d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 4) C4725
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

инструкция может оказаться неправильной на некоторых процессорах Pentium  
  
 Код содержит инструкцию встроенной сборки, которая может возвратить неточные результаты на некоторых микропроцессорах Pentium.  
  
 Следующий пример приводит к возникновению ошибки C4725.  
  
```  
// C4725.cpp // compile with: /W4 // processor: x86 double m32fp = 2.0003e-17; void f() { __asm { FDIV m32fp   // C4725 } } int main() { }  
```