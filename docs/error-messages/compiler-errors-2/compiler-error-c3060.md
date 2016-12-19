---
title: "Ошибка компилятора C3060 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3060"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3060"
ms.assetid: 6282bb92-0546-4b59-9435-d3840bf93bdb
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3060
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"член": дружественную функцию нельзя определить внутри класса с помощью полного имени \(ее можно только объявить\)  
  
 Дружественная функция была определена с помощью полного имени, что не допускается.  
  
 В следующем примере возникает ошибка C3060.  
  
```  
// C3060.cpp class A { public: void func(); }; class C { public: friend void A::func() { }   // C3060 // Try the following line and the out of class definition: // friend void A::func(); }; // void A::func(){}  
```