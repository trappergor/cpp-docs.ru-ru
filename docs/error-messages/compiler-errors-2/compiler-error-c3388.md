---
title: "Ошибка компилятора C3388 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3388"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3388"
ms.assetid: 34336545-ed13-4d81-ab5f-f869799fe4c2
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# Ошибка компилятора C3388
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": не допускается в качестве ограничения; предполагается, что "класс ref" продолжит синтаксический разбор  
  
 Ограничение для универсального типа указано неправильно. Дополнительные сведения см. в разделе [Ограничения, применяемые к параметрам универсальных типов \(C\+\+\/CLI\)](../Topic/Constraints%20on%20Generic%20Type%20Parameters%20\(C++-CLI\).md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3388:  
  
```  
// C3388.cpp // compile with: /clr /c interface class AA {}; generic <class T> where T : interface class   // C3388 ref class C {}; // OK generic <class T> where T : AA ref class D {};  
```