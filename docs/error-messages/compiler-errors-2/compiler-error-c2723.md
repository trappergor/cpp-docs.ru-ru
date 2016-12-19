---
title: "Ошибка компилятора C2723 | Microsoft Docs"
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
  - "C2723"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2723"
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2723
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

function: недопустимый описатель specifier в определении функции  
  
 Описатель не может использоваться в определении функции вне объявления класса.  Описатель `virtual` может быть указан только в объявлении функции\-члена внутри объявления класса.  
  
 В следующем примере показано возникновение ошибки C2723 и приводятся сведения по ее устранению.  
  
```  
// C2723.cpp  
struct X {  
   virtual void f();  
   virtual void g();  
};  
  
virtual void X::f() {}   // C2723  
  
// try the following line instead  
void X::g() {}  
```