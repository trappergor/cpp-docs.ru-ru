---
title: "Функция swap (auto_handle) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::swap"
  - "msclr.swap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "swap - функция"
ms.assetid: 7dd91b5c-f0de-4634-a2e2-642626706e27
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Функция swap (auto_handle)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Объекты обеспечивает обмен данными между двумя `auto_handle` и другими.  
  
## Синтаксис  
  
```  
template<typename _element_type>  
void swap(  
   auto_handle<_element_type> % _left,  
   auto_handle<_element_type> % _right  
);  
```  
  
#### Параметры  
 `_left`  
 Объект `auto_handle`.  
  
 `_right`  
 Другой объект `auto_handle`.  
  
## Пример  
  
```  
// msl_swap_auto_handle.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
using namespace System;  
using namespace msclr;  
  
int main() {  
   auto_handle<String> s1 = "string one";  
   auto_handle<String> s2 = "string two";  
  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
   swap( s1, s2 );  
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",  
      s1->ToString(), s2->ToString() );  
}  
```  
  
  **s1 \= «строка» одно, s2 \= «строка» 2**  
**s1 \= «строка» 2, s2 \= строка «один»**   
## Требования  
 **Файл заголовка**\<msclr\\auto\_handle.h\>  
  
 **Пространство имен** msclr  
  
## См. также  
 [auto\_handle](../dotnet/auto-handle.md)   
 [auto\_handle::swap](../dotnet/auto-handle-swap.md)