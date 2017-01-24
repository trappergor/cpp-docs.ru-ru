---
title: "Предупреждение компилятора (уровень 1) C4624 | Microsoft Docs"
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
  - "C4624"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4624"
ms.assetid: 14f61769-d92e-482b-9515-debd87b30a66
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4624
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

derived class: не удалось создать деструктор, так как деструктор для базового класса недоступен или удален  
  
 Деструктор был недоступен или удален в базовом классе, поэтому он не был создан для производного класса.  Любая попытка создать объект этого типа в стеке приведет к ошибке компилятора.  
  
 В следующем примере показано возникновение ошибки C4624 и приводятся сведения по ее устранению.  
  
```  
// C4624.cpp  
// compile with: /W1 /c  
class B {  
// Uncomment the following line to fix.  
// public:  
   ~B();  
};  
  
class D : public B {};   // C4624 B's destructor not public  
```