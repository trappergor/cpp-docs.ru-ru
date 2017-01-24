---
title: "Предупреждение компилятора (уровень 3) C4645 | Microsoft Docs"
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
  - "C4645"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4645"
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 3) C4645
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

функция, объявленная с атрибутом \_\_declspec\(noreturn\) имеет оператор return  
  
 Оператор [return](../Topic/return%20Statement%20in%20Program%20Termination%20\(C++\).md) найден в функции, помеченной модификатором [noreturn](../../cpp/noreturn.md) `__declspec`. Оператор `return` был пропущен.  
  
 Следующий пример приводит к возникновению ошибки C4645.  
  
```  
// C4645.cpp // compile with:  /W3 void __declspec(noreturn) func() { return;   // C4645, delete this line to resolve } int main() { }  
```