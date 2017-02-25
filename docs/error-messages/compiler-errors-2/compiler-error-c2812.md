---
title: "Ошибка компилятора C2812 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2812"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2812"
ms.assetid: 22aadb8c-7232-489d-a3ad-60662dda30a8
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка компилятора C2812
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#import не поддерживается \/clr:pure и \/clr:safe  
  
 [Директива \#import](../Topic/%23import%20Directive%20\(C++\).md) не поддерживается **\/clr:pure** и **\/clr:safe**, так как `#import` требует использования библиотек поддержки собственного компилятора.  
  
## Пример  
 В следующем примере формируется сообщение об ошибке C2812.  
  
```  
// C2812.cpp  
// compile with: /clr:pure /c  
#import "importlib.tlb"   // C2812  
```