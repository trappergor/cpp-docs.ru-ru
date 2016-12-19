---
title: "Ошибка компилятора C3536 | Microsoft Docs"
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
  - "C3536"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3536"
ms.assetid: 8d866075-866b-49eb-9979-ee27b308f7e3
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3536
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"символ": должен быть инициализирован перед использованием  
  
 Указывает на то, что символ должен быть инициализирован перед использованием.  Практически это означает, что переменную нельзя использовать для инициализации самой себя.  
  
### Исправление этой ошибки  
  
1.  Не используйте переменную для инициализации самой себя.  
  
## Пример  
 Следующий пример вызывает ошибку C3536, поскольку каждая переменная инициализирует саму себя.  
  
```  
// C3536.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto a = a;     //C3536  
   auto b = &b;    //C3536  
   auto c = c + 1; //C3536  
   auto* d = &d;   //C3536  
   auto& e = e;    //C3536  
   return 0;  
};  
```  
  
## См. также  
 [Ключевое слово auto](../../cpp/auto-keyword.md)