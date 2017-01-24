---
title: "Ошибка компилятора C3298 | Microsoft Docs"
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
  - "C3298"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3298"
ms.assetid: 458c2680-95bb-4d5e-895f-ce4115844193
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3298
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"ограничение\_1": невозможно использовать "ограничение\_2" как ограничение, поскольку "ограничение\_2" имеет ограничение ссылки, а "ограничение\_1" имеет ограничение значения  
  
 Нельзя указывать взаимно исключающие характеристики для ограничения. Например, параметр универсального типа не может быть ограничен одновременно типом значения и ссылочным типом.  
  
 Для получения дополнительной информации см. [Ограничения, применяемые к параметрам универсальных типов \(C\+\+\/CLI\)](../Topic/Constraints%20on%20Generic%20Type%20Parameters%20\(C++-CLI\).md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3298.  
  
```  
// C3298.cpp // compile with: /clr /c generic<class T, class U> where T : ref class where U : T, value class   // C3298 public ref struct R {};  
```