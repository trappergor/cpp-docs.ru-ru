---
title: "Ошибка компилятора C2553 | Microsoft Docs"
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
  - "C2553"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2553"
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2553
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"базовая\_функция": возвращаемый тип переопределенной функции отличается от "базовой\_функции"  
  
 Функция в производном классе совершила попытку переопределить виртуальную функцию в базовом классе, однако функция производного класса не получила тот же тип возвращаемого значения, что и функция базового класса.  Подпись переопределяющей функции должна соответствовать подписи переопределяемой функции.  
  
 Следующий пример приводит к возникновению ошибки C2553:  
  
```  
// C2553.cpp  
// compile with: /clr /c  
ref struct C {  
   virtual void f();  
};  
  
ref struct D : C {  
   virtual int f() override ;   // C2553   
  
   // try the following line instead  
   // virtual void f() override;  
};  
```