---
title: "Ошибка компилятора C3626 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3626"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3626"
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C3626
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"ключевое слово": ключевое слово "\_\_event" можно использовать только в интерфейсах COM, функциях\-членах и данных\-членах, являющихся указателями на делегатов  
  
 Ключевое слово использовалось неправильно.  
  
 Следующий пример приводит к возникновению ошибки C3626:  
  
```  
// C3626.cpp  
// compile with: /c  
struct A {  
   __event int i;   // C3626  
// try the following line instead  
// __event int i();  
};  
```