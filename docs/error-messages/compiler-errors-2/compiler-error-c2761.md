---
title: "Ошибка компилятора C2761 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2761"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2761"
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2761
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция" : повторное объявление функций\-членов не допускается  
  
 Функции\-члены нельзя объявлять повторно.  Их можно определять, но повторно объявлять их нельзя.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2761.  
  
```  
// C2761.cpp  
class a {  
   int t;  
   void test();  
};  
  
void a::a;     // C2761  
void a::test;  // C2761  
  
```  
  
## Пример  
 Нестатические члены структуры или класса не могут иметь определение.  Следующий пример приводит к возникновению ошибки C2761.  
  
```  
// C2761_b.cpp  
// compile with: /c  
struct C {  
   int s;  
   static int t;  
};  
  
int C::s;   // C2761  
int C::t;   // OK  
```