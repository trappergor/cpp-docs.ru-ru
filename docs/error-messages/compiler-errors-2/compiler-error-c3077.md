---
title: "Ошибка компилятора C3077 | Microsoft Docs"
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
  - "C3077"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3077"
ms.assetid: d9f3c619-d1e2-4656-81a5-a35a9586a7d4
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3077
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"метод\_завершения": метод завершения может быть членом только ссылочного типа  
  
 Нельзя объявлять метод завершения с собственным типом или типом значения.  
  
 Дополнительные сведения см. в разделе [Деструкторы и методы завершения в Visual C\+\+](../../misc/destructors-and-finalizers-in-visual-cpp.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3077.  
  
```  
// C3077.cpp // compile with: /clr /c value struct vs { !vs(){}   // C3077 }; ref struct rs { protected: !rs(){}   // OK };  
```