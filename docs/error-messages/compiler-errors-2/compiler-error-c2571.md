---
title: "Ошибка компилятора C2571 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2571"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2571"
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2571
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция" : объединение "объединение" не может содержать виртуальные функции  
  
 В объявлении объединения присутствует виртуальная функция.  Виртуальные функции можно объявлять только в структурах или классах.  Возможные способы разрешения:  
  
1.  Преобразуйте объединение в структуру или класс.  
  
2.  Не делайте функцию виртуальной.  
  
 Следующий пример приводит к возникновению ошибки C2571:  
  
```  
// C2571.cpp  
// compile with: /c  
union A {  
   virtual void func1();   // C2571  
   void func2();   // OK  
};  
```