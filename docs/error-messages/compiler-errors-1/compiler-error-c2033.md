---
title: "Ошибка компилятора C2033 | Microsoft Docs"
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
  - "C2033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2033"
ms.assetid: fd5a1637-9db2-4c98-a7cc-b63b39737cd9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": битовое поле не может иметь косвенное обращение  
  
 Битовое поле было объявлено как указатель, что не допускается.  
  
 Следующий пример приводит к возникновению ошибки C2033.  
  
```  
// C2033.cpp struct S { int *b : 1;  // C2033 };  
```  
  
 Возможное решение:  
  
```  
// C2033b.cpp // compile with: /c struct S { int b : 1; };  
```