---
title: "Ошибка компилятора C3485 | Microsoft Docs"
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
  - "C3485"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3485"
ms.assetid: d67536f9-67a1-4ad9-9a94-d8bbbca3d0dc
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3485
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

определение лямбда\-выражения не может содержать cv\-квалификаторы  
  
 Нельзя использовать квалификатор `const` или `volatile` как часть определения лямбда\-выражения.  
  
### Исправление ошибки  
  
-   Удалите квалификатор `const` или `volatile` из определения лямбда\-выражения.  
  
## Пример  
 Приведенный ниже пример приводит к возникновению ошибки C3485, так как в нем квалификатор `const` используется как часть определения лямбда\-выражения.  
  
```  
// C3485.cpp int main() { auto x = []() const mutable {}; // C3485 }  
```  
  
## См. также  
 [Лямбда\-выражения](../../cpp/lambda-expressions-in-cpp.md)