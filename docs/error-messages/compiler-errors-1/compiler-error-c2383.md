---
title: "Ошибка компилятора C2383 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2383"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2383"
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Ошибка компилятора C2383
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"символ": аргументы по умолчанию не разрешены для этого символа  
  
 Компилятор C\+\+ не допускает использование аргументов по умолчанию для указателей на функции.  
  
 Этот код принимался компилятором предыдущих версий, но теперь приводит к возникновению ошибки.  Для кода, который работает во всех версиях Visual C\+\+: не следует присваивать аргументу указателя на функцию значение по умолчанию.  
  
 Следующая строка вызывает ошибку C2383.  
  
```  
// C2383.cpp  
// compile with: /c   
void (*pf)(int = 0);   // C2383  
void (*pf)(int);   // OK  
```