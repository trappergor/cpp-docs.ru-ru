---
title: "Вызов функций C во встроенной сборке | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm - ключевое слово [C++], вызывающие функции"
  - "вызовы функций, функции C"
  - "вызовы функций, встроенная сборка"
  - "функции [C], вызов во встроенной сборке"
  - "встроенная сборка, вызывающие функции"
  - "Visual C, функции"
ms.assetid: f8a8d568-d175-4e23-9b24-36ef60a4cab3
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Вызов функций C во встроенной сборке
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Майкрософт  
 Блок `__asm` может вызывать функции языка C, включая библиотечные процедуры языка C.  В следующем примере вызывается библиотечная процедура `printf`.  
  
```  
// InlineAssembler_Calling_C_Functions_in_Inline_Assembly.cpp  
// processor: x86  
#include <stdio.h>  
  
char format[] = "%s %s\n";  
char hello[] = "Hello";  
char world[] = "world";  
int main( void )  
{  
   __asm  
   {  
      mov  eax, offset world  
      push eax  
      mov  eax, offset hello  
      push eax  
      mov  eax, offset format  
      push eax  
      call printf  
      //clean up the stack so that main can exit cleanly  
      //use the unused register ebx to do the cleanup  
      pop  ebx  
      pop  ebx  
      pop  ebx  
   }  
}  
```  
  
 Так как аргументы функции передается в стеке, перед вызовом функции просто поместите в стек требуемые аргументы \(в предыдущем примере это указатели строк\).  Аргументы помещаются в стек в обратном порядке, поэтому они извлекаются из стека в требуемом порядке.  Эмуляция оператора C  
  
```  
printf( format, hello, world );  
```  
  
 В этом примере в стек помещаются указатели на строки `world`, `hello` и `format` \(в этом порядке\), затем вызывается процедура `printf`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## См. также  
 [Встроенный ассемблер](../../assembler/inline/inline-assembler.md)