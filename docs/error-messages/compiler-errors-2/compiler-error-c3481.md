---
title: "Ошибка компилятора C3481 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3481"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3481"
ms.assetid: 5d09375a-5ed3-4b61-86ed-45e91fd734c7
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C3481
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

var: переменная, передаваемая в лямбда\-выражение, не найдена  
  
 Компилятору не удалось найти определение переменной, которая передается в список передаваемых параметров в лямбда\-выражении.  
  
### Исправление ошибки  
  
-   Удалите переменную из списка передаваемых параметров в лямбда\-выражении.  
  
## Пример  
 В следующем примере возникает ошибка C3481, так как переменная `n` не определена:  
  
```  
// C3481.cpp int main() { [n] {}(); // C3481 }  
```  
  
## См. также  
 [Лямбда\-выражения](../../cpp/lambda-expressions-in-cpp.md)