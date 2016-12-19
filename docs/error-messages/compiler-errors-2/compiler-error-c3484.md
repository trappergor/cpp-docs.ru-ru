---
title: "Ошибка компилятора C3484 | Microsoft Docs"
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
  - "C3484"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3484"
ms.assetid: 2fe847fa-f6ee-4978-bc1d-b6dc6ae906ac
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3484
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

требуется "\-\>" перед типом возврата  
  
 Необходимо указать `->` перед типом возврата лямбда\-выражения.  
  
### Исправление ошибки  
  
-   Укажите `->` перед типом возврата.  
  
## Пример  
 В следующем примере возникает ошибка C3484:  
  
```  
// C3484a.cpp int main() { return []() . int { return 42; }(); // C3484 }  
```  
  
## Пример  
 В следующем примере устраняется ошибка C3484 путем предоставления `->` перед типом возврата лямбда\-выражения:  
  
```  
// C3484b.cpp int main() { return []() -> int { return 42; }(); }  
```  
  
## См. также  
 [Лямбда\-выражения](../../cpp/lambda-expressions-in-cpp.md)