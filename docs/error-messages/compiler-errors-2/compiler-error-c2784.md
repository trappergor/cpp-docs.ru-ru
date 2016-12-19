---
title: "Ошибка компилятора C2784 | Microsoft Docs"
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
  - "C2784"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2784"
ms.assetid: 3d761fe2-881c-48bd-afae-e2e714e20473
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2784
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

declaration: не удалось вывести аргумент шаблона для type из type  
  
 Компилятор не может определить аргумент шаблона на основе представленных аргументов функции.  
  
 В следующем примере показано возникновение ошибки C2784 и приводятся сведения по ее устранению.  
  
```  
// C2784.cpp  
template<class T> class X {};  
template<class T> void f(X<T>) {}  
  
int main() {  
   X<int> x;  
   f(1);   // C2784  
  
   // To fix it, try the following line instead  
   f(x);  
}  
```