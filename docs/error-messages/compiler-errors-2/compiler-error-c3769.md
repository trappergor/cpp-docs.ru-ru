---
title: "Ошибка компилятора C3769 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3769"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3769"
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Ошибка компилятора C3769
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип" : вложенный класс не может иметь то же имя, что и класс, в котором он непосредственно содержится  
  
 Вложенный класс не может иметь то же имя, что и класс, в котором он непосредственно содержится.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3769.  
  
```  
// C3769.cpp  
// compile with: /c  
class x {  
   class x {};   // C3769  
   class y {  
      class x{};   // OK  
   };  
};  
```