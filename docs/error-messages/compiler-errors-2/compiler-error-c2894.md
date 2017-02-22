---
title: "Ошибка компилятора C2894 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2894"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2894"
ms.assetid: 4e250579-2b59-4993-a6f4-49273e7ecf06
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2894
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

объявление шаблонов с C\-компоновкой не допускается  
  
 Данная ошибка может возникать из\-за шаблона, определенного в блоке "С" `extern` .  
  
 Следующий пример приводит к возникновению ошибки C2894:  
  
```  
// C2894.cpp  
extern "C" {  
   template<class T> class stack {};   // C2894 fail  
  
   template<class T> void f(const T &aT) {}   // C2894  
}  
```  
  
 Следующий пример приводит к возникновению ошибки C2894:  
  
```  
// C2894b.cpp  
// compile with: /c  
extern "C" template<class T> void f(const T &aT) {}   // C2894  
  
template<class T> void f2(const T &aT) {}   // OK  
```