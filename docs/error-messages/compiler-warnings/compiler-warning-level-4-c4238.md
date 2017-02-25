---
title: "Предупреждение компилятора (уровень 4) C4238 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4238"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4238"
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора (уровень 4) C4238
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

использование нестандартного расширения: значение rvalue класса использовано как значение lvalue  
  
 Для совместимости с предыдущими версиями Visual C\+\+ расширения Microsoft \(**\/Ze**\) позволяют использование типа класса как значение rvalue в контексте, который явно или неявно принимает его адрес.  В некоторых случаях, как показано в следующем примере, это может быть небезопасным.  
  
## Пример  
  
```  
// C4238.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
C * pC = &C();   // C4238  
```  
  
 Подобное использование является причиной возникновения ошибки при совместимости с ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\).