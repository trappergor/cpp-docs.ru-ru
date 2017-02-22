---
title: "Ошибка компилятора C2452 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2452"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2452"
ms.assetid: a4ec7642-6660-4c7a-9866-853d1cc67daf
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C2452
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

type: недопустимый тип источника для safe\_cast  
  
 Тип источника [safe\_cast](../../windows/safe-cast-cpp-component-extensions.md) является недопустимым.  Например, при выполнении операции `safe_cast` должны использоваться только типы CLR.  
  
 Следующий пример приводит к возникновению ошибки C2452:  
  
```  
// C2452.cpp  
// compile with: /clr  
  
struct A {};  
struct B : public A {};  
  
ref struct C {};  
ref struct D : public C{};  
  
int main() {  
   A a;  
   safe_cast<B*>(&a);   // C2452  
  
   // OK  
   C ^ c = gcnew C;  
   safe_cast<D^>(c);  
}  
```