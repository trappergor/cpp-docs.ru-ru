---
title: "Ошибка компилятора C3295 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3295"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3295"
ms.assetid: 83f0aa4d-0e0a-4905-9f66-fcf9991fc07a
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# Ошибка компилятора C3295
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\#pragma \<директива pragma\>" может использоваться только в глобальной области или в области пространства имен  
  
 Некоторые директивы pragma нельзя использовать в функции.  Дополнительные сведения см. в разделе [Директивы Pragma и ключевое слово \_\_Pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3295:  
  
```  
// C3295.cpp int main() { #pragma managed   // C3295 }  
```