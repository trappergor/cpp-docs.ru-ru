---
title: "Ошибка компилятора C3399 | Microsoft Docs"
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
  - "C3399"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3399"
ms.assetid: 306ad199-d150-4f6c-bcf1-24a7948b93be
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3399
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": не удается предоставить аргументы при создании экземпляра универсального параметра  
  
 При указании ограничения `gcnew()` можно указать что тип ограничения будет иметь конструктор без параметров. Таким образом, при попытке создания экземпляра этого типа и передачи параметра возникает эта ошибка.  
  
 Дополнительные сведения см. в разделе [Ограничения, применяемые к параметрам универсальных типов \(C\+\+\/CLI\)](../Topic/Constraints%20on%20Generic%20Type%20Parameters%20\(C++-CLI\).md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3399.  
  
```  
// C3399.cpp // compile with: /clr /c generic <class T> where T : gcnew() void f() { T t = gcnew T(1);   // C3399 T t2 = gcnew T();   // OK }  
```