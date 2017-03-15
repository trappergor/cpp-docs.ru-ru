---
title: "Предупреждение компилятора (уровень 4) C4510 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4510"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4510"
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 4) C4510
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"класс": не удалось создать конструктор по умолчанию  
  
 Компилятору не удалось создать конструктор по умолчанию для указанного класса и не было создано ни одного пользовательского конструктора.  Невозможно создавать объекты этого типа.  
  
 Существует несколько случаев, при которых компилятору не удается создать конструктор по умолчанию. К ним относятся:  
  
-   Константный член данных.  
  
-   Член данных, который является ссылкой.  
  
 Необходимо создать пользовательский конструктор по умолчанию для класса, который инициализирует эти члены.  
  
 Следующий пример приводит к возникновению ошибки C4510:  
  
```  
// C4510.cpp  
// compile with: /W4  
struct A {  
   const int i;  
   int &j;  
   A& operator=( const A& ); // C4510 expected  
   // uncomment the following line to resolve this C4510  
   // A(int ii, int &jj) : i(ii), j(jj) {}  
};   // C4510  
  
int main() {  
}  
```