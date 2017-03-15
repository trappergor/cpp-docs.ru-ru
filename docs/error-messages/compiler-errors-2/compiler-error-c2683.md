---
title: "Ошибка компилятора C2683 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2683"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2683"
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C2683
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"приведение" : "тип" не является полиморфным типом  
  
 Вы не можете использовать [dynamic\_cast](../../cpp/dynamic-cast-operator.md) для преобразования из неполиморфного класса \(класса без виртуальных функций\).  
  
 Для преобразования неполиморфных типов вы можете использовать [static\_cast](../../cpp/static-cast-operator.md).  Однако `static_cast` не выполняет проверки времени выполнения.  
  
 Следующий пример приводит к возникновению ошибки C2683:  
  
```  
// C2683.cpp  
// compile with: /c  
class B { };  
class D : public B { };  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  // C2683  
   D* pd1 = static_cast<D*>(pb);   // OK  
}  
```