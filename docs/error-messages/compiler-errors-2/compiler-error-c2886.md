---
title: "Ошибка компилятора C2886 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2886"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2886"
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2886
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс::идентификатор" : символ не может использоваться в using\-объявлении члена  
  
 В объявлении с ключевым словом `using` используется такой символ, как, например, имя пространства имен.  `using`\-объявления предназначены для объявления членов базовых классов.  
  
 Следующий пример приводит к возникновению ошибки C2886:  
  
```  
// C2886.cpp  
// compile with: /c  
namespace Z {  
    int i;  
}  
  
class B {  
protected:  
    int i;  
};  
  
class D : public B {  
    // Error: Z is a namespace  
    using Z::i;   // C2886  
  
    // OK: B is a base class  
    using B::i;  
};  
```