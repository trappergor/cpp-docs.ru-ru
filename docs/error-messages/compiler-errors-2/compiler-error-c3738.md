---
title: "Ошибка компилятора C3738 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3738"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3738"
ms.assetid: dd3ee011-e204-4264-bf3a-da32c4ef7038
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C3738
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"cоглашение вызова": соглашение вызова при явном создании экземпляров должно соответствовать соглашению вызова для шаблона создаваемых экземпляров  
  
 Рекомендуется не указывать соглашение вызова для явного создания экземпляра.  Если же это необходимо, то соглашение должно быть соответствующим.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C3738.  
  
```  
// C3738.cpp  
// compile with: /clr  
// processor: x86  
#include <stdio.h>  
template< class T >  
void f ( T arg ) {   // by default calling convention is __cdecl  
   printf ( "f: %s\n", __FUNCSIG__ );  
}  
  
template   
void __stdcall f< int > ( int arg );   // C3738  
// try the following line instead  
// void f< int > ( int arg );  
  
int main () {  
   f(1);  
   f< int > ( 1 );  
}  
```