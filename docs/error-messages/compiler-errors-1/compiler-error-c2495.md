---
title: "Ошибка компилятора C2495 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2495"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2495"
ms.assetid: bb7066fe-3549-4901-97e4-157f3c04dd57
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2495
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

идентификатор: параметр "nothrow" может применяться только в объявлениях или определениях функций  
  
 Расширенный атрибут [nothrow](../Topic/nothrow%20\(C++\).md) может быть применен только к объявлению или определению функции.  
  
 Следующий пример приводит к возникновению ошибки C2495:  
  
```  
// C2495.cpp  
// compile with: /c  
__declspec(nothrow) class X {   // C2495  
   int m_data;  
} x;  
  
__declspec(nothrow) void test();   // OK  
```