---
title: "Ошибка компилятора C2502 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2502"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2502"
ms.assetid: affa0b86-15fc-4e17-b7f2-6aad4a3771c4
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2502
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": слишком много модификаторов доступа для базового класса  
  
 Для базового класса задано несколько модификаторов доступа.  Допускается наличие только одного модификатора доступа \(`public`, `private` или `protected`\).  
  
 Следующий пример приводит к возникновению ошибки C2502:  
  
```  
// C2502.cpp  
// compile with: /c  
class A { };  
class B { };  
class C : private public A { };   // C2502  
  
// OK  
class D : private A {};  
class E : public A, private B {};  
```