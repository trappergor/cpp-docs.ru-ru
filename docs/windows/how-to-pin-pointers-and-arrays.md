---
title: "Практическое руководство. Закрепление указателей и массивов | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "массивы [C++], закрепление"
  - "указатели, закрепление"
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Практическое руководство. Закрепление указателей и массивов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Закрепление части объекта, определенной в управляемом объекте, имеет эффект закрепления всего объекта.  Например, если закреплен любой элемент массива, весь массив также закреплен.  В языке нет расширений для объявления закрепленного массива.  Для закрепления массива, объявите закрепляющий указатель на тип элемента, и прикрепите один из элементов массива.  
  
## Пример  
  
### Код  
  
```  
// pin_ptr_array.cpp  
// compile with: /clr  
#include <stdio.h>  
using namespace System;  
  
int main() {  
   array<Byte>^ arr = gcnew array<Byte>(4);  
   arr[0] = 'C';  
   arr[1] = '+';  
   arr[2] = '+';  
   arr[3] = '\0';  
   pin_ptr<Byte> p = &arr[1];   // entire array is now pinned  
   unsigned char * cp = p;  
  
   printf_s("%s\n", cp); // bytes pointed at by cp  
                         // will not move during call  
}  
```  
  
### Output  
  
```  
++  
```  
  
## См. также  
 [pin\_ptr \(C\+\+\/CLI\)](../Topic/pin_ptr%20\(C++-CLI\).md)