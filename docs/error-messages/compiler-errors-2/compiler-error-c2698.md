---
title: "Ошибка компилятора C2698 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2698"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2698"
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2698
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

объявление использования для "объявления 1" невозможно при существующем объявлении использования для "объявления 2"  
  
 Поскольку имеется [объявление использования](../../cpp/using-declaration.md) для члена данных, любое объявление использования в той же области, использующее то же имя, не разрешено, так как перегруженными могут быть только функции.  
  
 Следующий пример приводит к возникновению ошибки C2698:  
  
```  
// C2698.cpp  
struct A {  
   int x;  
};  
  
struct B {  
   int x;  
};  
  
struct C : A, B {  
   using A::x;  
   using B::x;   // C2698  
}  
```