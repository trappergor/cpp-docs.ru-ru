---
title: "Предупреждение компилятора (уровень 1) C4077 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4077"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4077"
ms.assetid: c2d28805-b33f-41ad-afba-33b3f788c649
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 1) C4077
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

неизвестный параметр check\_stack  
  
 Старая форма прагмы **check\_stack** используется с неизвестным аргументом. Аргумент должен быть `+`, `-`, `(on)`, `(off)` или быть пустым.  
  
 Компилятор игнорирует эту прагму и оставляет проверку стека неизмененной.  
  
## Пример  
  
```  
// C4077.cpp // compile with: /W1 /LD #pragma check_stack yes // C4077 #pragma check_stack +    // Correct old form #pragma check_stack (on) // Correct new form  
```