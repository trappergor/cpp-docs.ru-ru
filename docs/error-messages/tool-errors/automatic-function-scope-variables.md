---
title: "Автоматические переменные (область видимости функции) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "автоматические переменные"
  - "функции [C++], область действия"
  - "область действия, объявленная внутри функций"
  - "переменные, автоматическая"
ms.assetid: 6e1a14c2-1fb0-4937-8628-8d963cc35ed4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Автоматические переменные (область видимости функции)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Переменная, объявленная в функции, может использоваться только в пределах области видимости данной функции.  
  
```  
// LNK2019_AV.cpp  
// compile with: /c  
void test(void);  
  
static int lnktest3 = 3;  
int lnktest4 = 4;  
  
int main() {  
   static int lnktest1 = 1;  
   int lnktest2 = 2;  
   test();  
}  
```  
  
 а затем  
  
```  
// LNK2019_AV_2.cpp  
// compile with: LNK2019_AV.cpp  
// LNK2019 expected  
extern int lnktest1;  
extern int lnktest2;  
extern int lnktest3;  
extern int lnktest4;  
  
void test(void) {  
   int i = 0;  
   i = lnktest1;  
   i = lnktest2;  
   i = lnktest3;  
   i = lnktest4;   // OK  
}  
```  
  
## См. также  
 [Ошибка средств компоновщика LNK2019](../Topic/Linker%20Tools%20Error%20LNK2019.md)