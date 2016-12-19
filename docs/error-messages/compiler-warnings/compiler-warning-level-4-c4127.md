---
title: "Предупреждение компилятора (уровень&#160;4) C4127 | Microsoft Docs"
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
  - "C4127"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4127"
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
caps.latest.revision: 12
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень&#160;4) C4127
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

условное выражение является константой  
  
 Управляющее выражение оператора `if` или цикла `while` является константой. Если управляющее выражение цикла `while` является константой, так как цикл завершит работу в середине, рассмотрите возможность замены цикла `while` на цикл `for`. Можно опустить инициализацию, проверку завершения и шаг приращения цикла `for`, что приведет к бесконечному циклу \(как `while(1)`\), и выйти из цикла можно в теле оператора `for`.  
  
 Следующий пример приводит к возникновению ошибки C4127:  
  
```  
// C4127.cpp // compile with: /W4 #include <stdio.h> int main() { if (1 == 1) {}   // C4127 while (1) { break; }   // C4127 // OK for ( ; ; ) { printf("test\n"); break; } }  
```