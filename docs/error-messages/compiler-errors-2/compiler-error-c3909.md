---
title: "Ошибка компилятора C3909 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3909"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3909"
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C3909
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Объявление события WinRT или управляемого события должно находиться в типе WinRT или управляемом типе.  
  
 Событие среды выполнения Windows или управляемое событие было объявлено в собственном типе.  Чтобы устранить эту ошибку, объявите события в типах среды выполнения Windows или управляемых типах.  
  
 Дополнительные сведения см. в разделе, посвященном [событию](../../windows/event-cpp-component-extensions.md).  
  
 В следующем примере показано возникновение ошибки C3909 и приводятся сведения по ее устранению.  
  
```  
// C3909.cpp  
// compile with: /clr /c  
delegate void H();  
class X {  
   event H^ E;   // C3909 - use ref class X instead  
};  
  
ref class Y {  
   static event H^ E {  
      void add(H^) {}  
      void remove( H^ h ) {}  
      void raise( ) {}  
   }  
};  
```