---
title: "Ошибка компилятора C2106 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2106"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2106"
ms.assetid: d5c91a2e-04e4-4770-8478-788b98c52a53
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2106
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\<оператор\> : левый операнд должен быть L\-value  
  
 Оператор должен быть L\-value, поскольку это левый операнд.  
  
 Следующий пример приводит к возникновению ошибки C2106:  
  
```  
// C2106.cpp  
int main() {  
   int a;  
   1 = a;   // C2106  
   a = 1;   // OK  
}  
```