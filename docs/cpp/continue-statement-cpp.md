---
title: "Оператор continue (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "continue"
  - "continue_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "continue - ключевое слово [C++]"
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор continue (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Обеспечивает передачу управления управляющему выражению наименьшего внешнего цикла [do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md) или [while](../cpp/while-statement-cpp.md).  
  
## Синтаксис  
  
```  
continue;  
```  
  
## Заметки  
 Все остальные операторы текущей итерации не выполняются.  Следующая итерация цикла определяется следующим образом.  
  
-   В цикле `do` или `while` следующая итерация начинается путем повторного вычисления управляющего выражения оператора `do` или `while`.  
  
-   В цикле `for` \(в котором используется синтаксис `for`\(`init-expr`; `cond-expr`; `loop-expr`\)\) выполняется предложение `loop-expr`.  Затем повторно выполняется предложение `cond-expr` и, в зависимости от результата, цикл завершается или начинается другая итерация.  
  
 В следующем примере показано использование оператора `continue` для обхода фрагментов кода и начала выполнения следующей итерации цикла.  
  
## Пример  
  
```  
// continue_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        i++;  
        printf_s("before the continue\n");  
        continue;  
        printf("after the continue, should never print\n");  
     } while (i < 3);  
  
     printf_s("after the do loop\n");  
}  
```  
  
  **перед continue**  
**перед continue**  
**перед continue**  
**после цикла do**   
## См. также  
 [Операторы перехода](../cpp/jump-statements-cpp.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)