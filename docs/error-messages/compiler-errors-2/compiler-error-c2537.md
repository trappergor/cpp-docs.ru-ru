---
title: "Ошибка компилятора C2537 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2537"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2537"
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2537
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"спецификатор": недопустимая спецификация компоновки  
  
 Возможные причины:  
  
1.  Спецификатор компоновки не поддерживается.  Поддерживается только спецификатор компоновки в стиле "C".  
  
2.  Компоновка "C" задана для более чем одной функции в наборе перегруженных функций.  Это не допускается.  
  
 Следующий пример приводит к возникновению ошибки C2537:  
  
```  
// C2537.cpp  
// compile with: /c  
extern "c" void func();   // C2537  
extern "C" void func2();   // OK  
```