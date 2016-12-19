---
title: "Предупреждение компилятора (уровень&#160;1) C4822 | Microsoft Docs"
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
  - "C4822"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4822"
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень&#160;1) C4822
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"член": функция\-член локального класса не имеет тела  
  
 Функция\-член локального класса объявлена в классе, но не определена в нем. Чтобы использовать функцию\-член локального класса, необходимо определить ее внутри класса. Объявление функции в классе и определение функции за его пределами невозможно.  
  
 Любое определение функции\-члена локального класса вне класса вызовет ошибку.  
  
 Следующий пример приводит к возникновению предупреждения C4822:  
  
```  
// C4822.cpp // compile with: /W1 int main() { struct C { void func1(int);   // C4822 // try the following line instead // void func1(int){} }; }  
```