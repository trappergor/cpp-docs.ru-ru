---
title: "Ошибка компилятора C2688 | Microsoft Docs"
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
  - "C2688"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2688"
ms.assetid: 168c9e9d-8f65-4664-af86-db71d3e6ee46
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2688
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"C2::fgrv" : ковариантные возвращаемые значения с несколькими или виртуальными наследованиями не поддерживаются для функций "varargs"  
  
 Ковариантные возвращаемые значения возвращают типы, не поддерживаемые в Visual C\+\+, когда функция содержит переменные аргументы.  
  
 Чтобы разрешить эту ошибку, либо определите функции так, чтобы они не могли использовать переменные аргументы, либо сделайте значения возврата одинаковыми для всех виртуальных функций.  
  
 Следующий пример приводит к возникновению ошибки C2688:  
  
```  
// C2688.cpp  
struct G1 {};  
struct G2 {};  
struct G3 : G1, G2 {};  
struct G4 {};  
struct G5 {};  
struct G6 : G4, G5 {};  
struct G7 : G3, G6 {};  
  
struct C1 {  
   virtual G4& fgrv(int,...);  
};  
  
struct C2 : C1 {  
   virtual G7& fgrv(int,...);   // C2688, does not return G4&  
};  
```