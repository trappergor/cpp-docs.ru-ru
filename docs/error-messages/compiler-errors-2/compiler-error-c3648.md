---
title: "Ошибка компилятора C3648 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3648"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3648"
ms.assetid: 5d042989-41cb-4cd0-aa50-976b70146aaf
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C3648
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

данный синтаксис явного переопределения требует параметра \/clr:oldSyntax  
  
 При компиляции для последней версии управляемого синтаксиса компилятор обнаружил синтаксис явного переопределения для предыдущих версий.  
  
 Дополнительные сведения см. в разделе [Явное переопределение](../../windows/explicit-overrides-cpp-component-extensions.md).  Дополнительные сведения об использовании устаревшего синтаксиса см. в разделе [Явное переопределение](../../cpp/explicit-overrides-cpp.md).  
  
 Следующий пример приводит к возникновению ошибки C3648:  
  
```  
// C3648.cpp  
// compile with: /clr  
public interface struct I {  
   void f();  
};  
  
public ref struct R : I {  
   virtual void I::f() {}   // C3648  
   // try the following line instead  
   // virtual void f() = I::f{}  
};  
```