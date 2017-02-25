---
title: "Ошибка компилятора C2584 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2584"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2584"
ms.assetid: 836e2c0a-86c0-4742-b432-beb0191ad20e
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Ошибка компилятора C2584
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс": недоступный прямой базовый класс "базовый класс 2"; уже является базовым классом для "базовый класс 1"  
  
 `Class` уже наследуется напрямую от `Base1` `Base2` также является производным от `Base1`.  Класс `Class` не может являться производным от `Base2`, поскольку в этом случае неявно выполняется повторное наследование от `Base1`. Это недопустимо, поскольку `Base1` уже является прямым базовым классом.  
  
## Пример  
 В следующем примере возникает ошибка C2584.  
  
```  
// C2584.cpp  
// compile with: /c  
struct A1 {  
   virtual int MyFunction();  
};  
  
struct A2 {  
    virtual int MyFunction();  
};  
  
struct B1: public virtual A1, virtual A2 {  
    virtual int MyFunction();  
};  
  
struct B2: public virtual A2, virtual A1 {  
    virtual int MyFunction();  
};  
  
struct C: virtual B1, B2 {  
    virtual int MyFunction();  
};  
  
struct Z : virtual B2, virtual C {   // C2584  
// try the following line insted  
// struct Z : virtual C {  
    virtual int MyFunction();  
};  
```