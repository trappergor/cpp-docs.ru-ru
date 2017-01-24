---
title: "Ошибка компилятора C2548 | Microsoft Docs"
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
  - "C2548"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2548"
ms.assetid: 01e9c835-9bf3-4020-9295-5ee448c519f3
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2548
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс::член" : в списке параметров по умолчанию отсутствует параметр  
  
 В списке параметров по умолчанию отсутствует параметр.  При указании параметра по умолчанию в списке параметров для всех последующих параметров также следует указать значения по умолчанию.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2548:  
  
```  
// C2548.cpp  
// compile with: /c  
void func( int = 1, int, int = 3);  // C2548  
  
// OK  
void func2( int, int, int = 3);  
void func3( int, int = 2, int = 3);  
```