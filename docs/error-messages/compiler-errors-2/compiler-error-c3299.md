---
title: "Ошибка компилятора C3299 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3299"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3299"
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Ошибка компилятора C3299
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция\-член": невозможно указать ограничения, они унаследованы из базового метода  
  
 При переопределении универсальной функции\-члена нельзя указать предложения ограничений \(при повторении ограничений подразумевается, что они не наследуются\).  
  
 В этом случае наследуются предложения ограничений, содержащиеся в переопределяемой универсальной функции.  
  
 Дополнительные сведения см. в разделе [Ограничения, применяемые к параметрам универсальных типов \(C\+\+\/CLI\)](../Topic/Constraints%20on%20Generic%20Type%20Parameters%20\(C++-CLI\).md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3299.  
  
```  
// C3299.cpp // compile with: /clr /c public ref struct R { generic<class T> where T : R virtual void f(); }; public ref struct S : R { generic<class T> where T : R   // C3299 virtual void f() override; };  
```