---
title: "Предупреждение компилятора (уровень 4) C4668 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4668"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4668"
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора (уровень 4) C4668
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"символ" не определен в качестве макроса препроцессора и будет заменен в "директивах" на "0"  
  
 В директиве препроцессора использован символ, который не был определен.  Его значение будет ложным.  Символ можно определить с помощью директивы [\#define](../../preprocessor/hash-define-directive-c-cpp.md) или параметра компилятора [\/D](../../build/reference/d-preprocessor-definitions.md).  
  
 Данное предупреждение по умолчанию отключено.  Дополнительные сведения см. в разделе [Отключенные по умолчанию предупреждения компилятора](../Topic/Compiler%20Warnings%20That%20Are%20Off%20by%20Default.md).  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C4668:  
  
```  
// C4668.cpp  
// compile with: /W4  
#include <stdio.h>  
  
#pragma warning (default : 4668)   // turn warning on  
  
int main()   
{  
    #if q   // C4668, q is not defined  
        printf_s("defined");  
    #else  
        printf_s("undefined");  
    #endif  
}  
```