---
title: "function (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "function_CPP"
  - "vc-pragma.function"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "прагма функции"
  - "прагмы, функция"
ms.assetid: cbd1bd60-fabf-4b5a-9c3d-2d9f4b871365
caps.latest.revision: 10
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# function (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, что для функций из списка аргументов директивы \#pragma будут создаваться вызовы.  
  
## Синтаксис  
  
```  
  
#pragma function( function1 [, function2, ...] )  
```  
  
## Заметки  
 Если с помощью директивы \#pragma **intrinsic** \(или \/Oi\) компилятору задано, что требуется создавать встроенные функции \(встроенные функции создаются как встроенный код, а не как вызовы функций\), можно использовать директиву \#pragma **function**, чтобы явно принудительно задать вызов функции.  После появления директивы \#pragma она действует на первое определение функции, содержащее указанную встроенную функцию.  Действие продолжается до конца исходного файла или до появления директивы \#pragma **intrinsic**, указывающей ту же встроенную функцию.  Директива \#pragma **function** может использоваться только за пределами функции — на глобальном уровне.  
  
 Списки функций, имеющих встроенные формы, см. в разделе [\#pragma intrinsic](../preprocessor/intrinsic.md).  
  
## Пример  
  
```  
// pragma_directive_function.cpp  
#include <ctype.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
  
// use intrinsic forms of memset and strlen  
#pragma intrinsic(memset, strlen)  
  
// Find first word break in string, and set remaining  
// chars in string to specified char value.  
char *set_str_after_word(char *string, char ch) {  
   int i;  
   int len = strlen(string);  /* NOTE: uses intrinsic for strlen */  
  
   for(i = 0; i < len; i++) {  
      if (isspace(*(string + i)))   
         break;  
   }  
  
   for(; i < len; i++)   
      *(string + i) = ch;  
  
   return string;  
}  
  
// do not use strlen intrinsic  
#pragma function(strlen)  
  
// Set all chars in string to specified char value.  
char *set_str(char *string, char ch) {  
   // Uses intrinsic for memset, but calls strlen library function  
   return (char *) memset(string, ch, strlen(string));  
}  
  
int main() {  
   char *str = (char *) malloc(20 * sizeof(char));  
  
   strcpy_s(str, sizeof("Now is the time"), "Now is the time");  
   printf("str is '%s'\n", set_str_after_word(str, '*'));  
   printf("str is '%s'\n", set_str(str, '!'));  
}  
```  
  
  **str is 'Now\*\*\*\*\*\*\*\*\*\*\*\*'**  
**str is '\!\!\!\!\!\!\!\!\!\!\!\!\!\!\!'**   
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)