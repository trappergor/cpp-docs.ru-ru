---
title: "Ошибка компилятора C2180 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2180"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2180"
ms.assetid: ea71b39e-b977-48a7-b7bd-af68ef5e263b
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Ошибка компилятора C2180
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

управляющее выражение имеет тип type  
  
 Управляющее выражение в `if`, `while`, `for` или инструкция `do` — это выражение, приведенное к `void`.  Чтобы устранить эту проблему, измените управляющее выражение на то, что создает `bool` или тип, который можно преобразовать в `bool`.  
  
 Следующий пример приводит к возникновению ошибки C2180:  
  
```  
// C2180.c  
  
int main() {  
   while ((void)1)   // C2180  
      return 1;  
   while (1)         // OK  
      return 0;  
}  
```