---
title: "Ошибка компилятора C3496 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3496"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3496"
ms.assetid: e19885f2-677f-4c1e-bc69-e35852262dc3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C3496
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"this" всегда передается по значению: знак "&" проигнорирован  
  
 Нельзя передать указатель `this` по ссылке.  
  
### Исправление ошибки  
  
-   Передайте указатель `this` по значению.  
  
## Пример  
 Представленный ниже пример приводит к возникновению ошибки C3496, так как ссылка на указатель `this` присутствует в списке передачи лямбда\-выражения.  
  
```  
// C3496.cpp // compile with: /c class C { void f() { [&this] {}(); // C3496 } };  
```  
  
## См. также  
 [Лямбда\-выражения](../../cpp/lambda-expressions-in-cpp.md)