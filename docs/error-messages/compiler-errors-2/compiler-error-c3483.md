---
title: "Ошибка компилятора C3483 | Microsoft Docs"
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
  - "C3483"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3483"
ms.assetid: 18b3a2c5-dfc9-4661-9653-08a5798474cf
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3483
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

var уже является частью списка передаваемых параметров лямбда\-выражения  
  
 Вы несколько раз передали одну и ту же переменную в список передаваемых параметров лямбда\-выражения.  
  
### Исправление ошибки  
  
-   Удалите все дополнительные экземпляры переменной из списка передаваемых параметров.  
  
## Пример  
 В следующем примере возникает ошибка C3483, так как в списке передаваемых параметров лямбда\-выражения переменная `n` присутствует несколько раз.  
  
```  
// C3483.cpp int main() { int m = 6, n = 5; [m,n,n] { return n + m; }(); // C3483 }  
```  
  
## См. также  
 [Лямбда\-выражения](../../cpp/lambda-expressions-in-cpp.md)