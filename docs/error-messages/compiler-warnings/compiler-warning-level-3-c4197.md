---
title: "Предупреждение компилятора (уровень 3) C4197 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4197"
ms.assetid: f766feef-82b0-4d81-8a65-33628c7db196
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 3) C4197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"тип": входящее приведение volatile верхнего уровня игнорируется  
  
 Компилятор обнаружил преобразование к типу значения R, который определен как [volatile](../../cpp/volatile-cpp.md), или преобразование типа значения R в другой тип, определенный как volatile.  В соответствии со стандартом C \(6.5.3\), свойства, связанные с определенными типами, имеют смысл только для выражений с L\-значением.  
  
 Следующий пример приводит к возникновению ошибки C4197:  
  
```  
// C4197.cpp  
// compile with: /W3  
#include <stdio.h>  
#include <signal.h>  
#include <stdlib.h>  
  
void sigproc(int);  
struct S  
{  
   int i;  
} s;  
  
int main()  
{  
   signal(SIGINT, sigproc);  
   s.i = 1;  
   S *pS = &s;  
   for ( ; (volatile int)pS->i ; )   // C4197  
      break;  
   // for ( ; *(volatile int *)&pS->i ; )   // OK  
   //    break;  
}  
  
void sigproc(int) // ctrl-C  
{  
   signal(SIGINT, sigproc);  
   s.i = 0;  
}  
  
```