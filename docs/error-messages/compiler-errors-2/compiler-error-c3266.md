---
title: "Ошибка компилятора C3266 | Microsoft Docs"
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
  - "C3266"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3266"
ms.assetid: 7375c099-acb7-42f6-898d-57cfefa010b8
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3266
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс": список параметров конструктора класса должен иметь тип "void"  
  
 Конструкторы классов, программируемых с использованием параметра \/clr, не могут принимать параметры.  
  
 Следующий пример приводит к возникновению ошибки C3266:  
  
```  
// C3266.cpp // compile with: /clr ref class X { static X(int i) { // C3266 // try the following line instead // static X() { } }; int main() { }  
```  
  
 Следующий пример приводит к возникновению ошибки C3266:  
  
```  
// C3266b.cpp // compile with: /clr:oldSyntax #using <mscorlib.dll> __gc class X { static X(int i) { // C3266 // try the following line instead // static X() { } }; int main() { }  
```