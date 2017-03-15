---
title: "Ошибка компилятора C2753 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2753"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2753"
ms.assetid: 92bfeeac-524a-4a8e-9a4f-fb8269055826
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C2753
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс" : класс шаблона уже был определен  
  
 Если список аргументов шаблона соответствует списку параметров, компилятор воспринимает его как один и тот же шаблон.  Нельзя определить один и тот же шаблон дважды.  
  
 Следующий пример приводит к возникновению ошибки C2753:  
  
```  
// C2753.cpp  
template<class T>  
struct A {};  
  
template<class T>  
struct A<T> {};   // C2753  
// try the following line instead  
// struct A<int> {};  
  
template<class T, class U, class V, class W, class X>  
struct B {};  
```