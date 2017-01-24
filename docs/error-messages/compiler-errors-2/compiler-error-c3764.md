---
title: "Ошибка компилятора C3764 | Microsoft Docs"
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
  - "C3764"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3764"
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3764
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция\_переопределения": не удалось переопределить метод базового класса "функция\_базового\_класса"  
  
 Компилятор обнаружил некорректное переопределение.  Например, функция базового класса не являлась `virtual`.  Для получения дополнительной информации см. [override](../../windows/override-cpp-component-extensions.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3764.  
  
```  
// C3764.cpp  
// compile with: /clr /c  
public ref struct A {  
   void g(int);  
   virtual void h(int);  
};  
  
public ref struct B : A {  
   virtual void g(int) override {}   // C3764  
   virtual void h(int) override {}   // OK  
};  
```  
  
## Пример  
 Ошибка C3764 также может произойти при одновременном явном и именованном переопределении метода базового класса.  Следующий пример приводит к возникновению ошибки C3764.  
  
```  
// C3764_b.cpp  
// compile with: /clr /c  
ref struct A {  
   virtual void Test() {}  
};  
  
ref struct B : public A {  
   virtual void Test() override {}  
   virtual void Test2() = A::Test {}   // C3764  
};  
```