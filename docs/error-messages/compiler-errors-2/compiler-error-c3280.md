---
title: "Ошибка компилятора C3280 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3280"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3280"
ms.assetid: 86dc5bbc-8818-4786-a728-9334268d308b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3280
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс": функцию\-член управляемого типа нельзя скомпилировать как неуправляемую функцию  
  
 Функции\-члены управляемого типа нельзя компилировать как неуправляемые функции.  
  
 Следующий пример приводит к возникновению ошибки C3280:  
  
```  
// C3280_2.cpp // compile with: /clr ref struct A { void func(); }; #pragma managed(push,off) void A::func()   // C3280 { } #pragma managed(pop)  
```  
  
 Следующий пример приводит к возникновению ошибки C3280:  
  
```  
// C3280.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> __gc struct A { void func(); }; #pragma managed(push,off) void A::func()   // C3280 { } #pragma managed(pop)  
```