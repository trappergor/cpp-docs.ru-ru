---
title: "Ошибка компилятора C3421 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3421"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3421"
ms.assetid: b52050c6-17a4-424a-8894-337b0cec7010
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Ошибка компилятора C3421
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": невозможно вызвать метод завершения для данного класса, поскольку он либо недоступен, либо не существует  
  
 Метод завершения является неявно закрытым, поэтому его нельзя вызвать за пределами включающего типа.  
  
 Дополнительные сведения см. в разделе [Деструкторы и методы завершения в Visual C\+\+](../../misc/destructors-and-finalizers-in-visual-cpp.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3421:  
  
```  
// C3421.cpp // compile with: /clr ref class A {}; ref class B { !B() {} public: ~B() {} }; int main() { A a; a.!A();   // C3421 B b; b.!B();   // C3421 }  
```