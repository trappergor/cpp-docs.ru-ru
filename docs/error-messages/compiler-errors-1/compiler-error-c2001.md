---
title: "Ошибка компилятора C2001 | Microsoft Docs"
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
  - "C2001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2001"
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2001
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

новая строка в константе  
  
 Строковая константа не может продолжаться на новой строке, если не выполняются следующие условия:  
  
-   Первая строка завершается обратной косой чертой.  
  
-   Первая строка завершается двойной кавычкой, а следующая за ней строка начинается двойной кавычкой.  
  
 Недостаточно завершить первую строку символом "\\n".  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2001:  
  
```  
// C2001.cpp  
// C2001 expected  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,  
             world");  
    printf_s("Hello,\n  
             world");  
}  
```  
  
## Пример  
 Пробелы в начале следующей строки после знака продолжения строки включаются в строковую константу.  Ни в одном из приведенных выше примеров символ новой строки не включается в строковую константу.  Символ новой строки можно включить в строку следующим способом:  
  
```  
// C2001b.cpp  
#include <stdio.h>  
  
int main()  
{  
    printf_s("Hello,\n\  
             world");  
  
    printf_s("Hello,\  
             \nworld");  
  
    printf_s("Hello,\n"  
             "world");  
  
    printf_s("Hello,"  
             "\nworld");  
  
    printf_s("Hello,"  
             " world");  
  
    printf_s("Hello,\  
             world");  
}  
```