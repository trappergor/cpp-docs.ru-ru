---
title: "Предупреждение компилятора (уровень 3) C4287 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4287"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4287"
ms.assetid: 1bf3bff8-6402-4d06-95ba-431678a790a7
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора (уровень 3) C4287
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"operator" : несовпадение отрицательной константы и константы без знака  
  
 В операции с отрицательным числом была использована неподписанная переменная.  
  
 Данное предупреждение по умолчанию отключено.  Дополнительные сведения см. в разделе [Отключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C4287:  
  
```  
// C4287.cpp  
// compile with: /W3  
#pragma warning(default : 4287)  
#include <stdio.h>  
  
int main()  
{  
    unsigned int u = 1;  
    if (u < -1)   // C4287  
        printf_s("u LT -1");  
    else  
        printf_s("u !LT -1");  
    return 0;  
}  
```