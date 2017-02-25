---
title: "Ошибка компилятора C2461 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2461"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2461"
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2461
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'class' : в синтаксисе конструктора отсутствуют формальные параметры  
  
 В конструкторе класса не указаны формальные параметры.  В объявлении конструктора необходимо указать хотя бы один формальный параметр. \(Список может быть пустым\).  
  
 Добавьте пару скобок после `class``::``class`.  
  
 Следующий пример приводит к возникновению ошибки C2461:  
  
```  
// C2461.cpp  
// compile with: /c  
class C {  
   C::C;   // C2461  
   C::C();   // OK  
};  
```