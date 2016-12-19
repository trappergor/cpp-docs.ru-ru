---
title: "Ошибка компилятора C2588 | Microsoft Docs"
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
  - "C2588"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2588"
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2588
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"::~identifier" : недопустимый глобальный деструктор  
  
 Деструктор определен не для класса, структуры или объединения.  Это не допускается.  
  
 Эта ошибка может быть вызвана отсутствующим классом, структурой или именем объединения слева от области оператора разрешения \(`::`\).  
  
 Следующий пример приводит к возникновению ошибки C2588:  
  
```  
// C2588.cpp  
~F();   // C2588  
```