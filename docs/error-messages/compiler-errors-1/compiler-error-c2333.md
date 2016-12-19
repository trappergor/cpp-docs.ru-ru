---
title: "Ошибка компилятора C2333 | Microsoft Docs"
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
  - "C2333"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2333"
ms.assetid: 2636fc1e-d3e7-4e68-8628-3c81a99ba813
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2333
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция": ошибка в объявлении функции; тело функции пропускается  
  
 Эта ошибка возникает после другой ошибки в функциях\-членах, определяемых внутри своего класса.  
  
 Следующий пример приводит к возникновению ошибки C2333:  
  
```  
// C2333.cpp  
struct s1 {  
   s1(s1) {}   // C2333  
};  
```