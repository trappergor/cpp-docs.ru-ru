---
title: "Ошибка компилятора C2969 | Microsoft Docs"
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
  - "C2969"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2969"
ms.assetid: e4ea3d66-b937-4b2c-b42a-96e03fb11579
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2969
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

синтаксическая ошибка: "символ": требуется закончить определение функции\-члена символом "}"  
  
 Определение функции\-члена шаблона имеет несовпадающую закрывающую фигурную скобку.  
  
 Следующий пример приводит к возникновению ошибки C2969:  
  
```  
// C2969.cpp // compile with: /c class A { int i; public: A(int i) {} }; A anA(1); class B { A a; B() : a(anA);   // C2969 // try the following line instead // B() : a(anA) {} };  
```