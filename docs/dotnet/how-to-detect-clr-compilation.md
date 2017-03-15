---
title: "Практическое руководство. Определение факта использования ключа /clr при компиляции | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/clr - параметр компилятора [C++], определение использования"
  - "компиляция, обнаружение /clr"
ms.assetid: a9310045-4810-4637-a64a-0b31a08791c1
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Практическое руководство. Определение факта использования ключа /clr при компиляции
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Для определения факта компиляции модуля с ключом **\/clr**, используйте макрос `_MANAGED` или `_M_CEE`.  Для получения дополнительной информации см. [\/clr \(компиляция CLR\)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Дополнительные сведения о макросах см. в разделе [Предустановленный макрос](../preprocessor/predefined-macros.md).  
  
## Пример  
  
```  
// detect_CLR_compilation.cpp  
// compile with: /clr  
#include <stdio.h>  
  
int main() {  
   #if (_MANAGED == 1) || (_M_CEE == 1)  
      printf_s("compiling with /clr\n");  
   #else  
      printf_s("compiling without /clr\n");  
   #endif  
}  
```  
  
## См. также  
 [Использование взаимодействия языка C\+\+ \(неявный PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)