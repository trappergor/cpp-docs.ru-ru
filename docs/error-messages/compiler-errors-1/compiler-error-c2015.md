---
title: "Ошибка компилятора C2015 | Microsoft Docs"
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
  - "C2015"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2015"
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2015
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

слишком много знаков в константе  
  
 Символьная константа содержит более двух знаков.  Число знаков в стандартных и длинных символьных константах ограничено одним и двумя соответственно.  
  
 Escape\-последовательность, например \\t, преобразуется в один знак.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2015:  
  
```  
// C2015.cpp  
// compile with: /c  
  
char test1 = 'error';   // C2015  
char test2 = 'e';   // OK  
```  
  
## Пример  
 Ошибка C2015 также может возникать в случае преобразования символьных констант в целые числа при использовании расширения Microsoft.  Следующий пример приводит к возникновению ошибки C2015:  
  
```  
// C2015b.cpp  
#include <stdio.h>  
  
int main()   
{  
    int a = 'abcde';   // C2015  
  
    int b = 'a';   // 'a' = ascii 0x61  
    printf_s("%x\n", b);  
}  
```