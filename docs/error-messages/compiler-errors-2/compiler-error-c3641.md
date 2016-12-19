---
title: "Ошибка компилятора C3641 | Microsoft Docs"
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
  - "C3641"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3641"
ms.assetid: e8d3613e-5e8d-46fe-a516-eb7d1de7cd21
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3641
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : недопустимое соглашение при вызове 'calling\_convention' для функции, скомпилированной с использованием параметра \/clr:pure или \/clr:safe  
  
 Только соглашение при вызове [\_\_clrcall](../../cpp/clrcall.md) допустимо при использовании параметра [\/clr:pure](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Следующий пример приводит к возникновению ошибки C3641:  
  
```  
// C3641.cpp  
// compile with: /clr:pure /c  
void __cdecl f() {}   // C3641  
```