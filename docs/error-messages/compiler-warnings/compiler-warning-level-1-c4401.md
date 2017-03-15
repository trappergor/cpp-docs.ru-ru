---
title: "Предупреждение компилятора (уровень 1) C4401 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4401"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4401"
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Предупреждение компилятора (уровень 1) C4401
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"битовоеполе": член является битовым полем  
  
 Встроенный код на языке ассемблера пытается обратиться к члену, являющемуся битовым полем.  Для встроенного кода ассемблера битовые поля\-члены недоступны, поэтому используется последняя граница упаковки перед членом, являющимся битовым полем.  
  
 Чтобы устранить это предупреждение, необходимо привести битовое поле к подходящему типу перед тем, как использовать его во встроенном коде на языке ассемблера.  Следующий пример приводит к возникновению ошибки C4401:  
  
```  
// C4401.cpp  
// compile with: /W1  
// processor: x86  
typedef struct bitfield {  
   signed bit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bf.bit = 0;  
   __asm {  
      mov bf.bit,0;   // C4401  
   }  
  
   /* use the following __asm block to resolve the warning  
   int i = (int)bf.bit;  
   __asm {  
      mov i,0;  
   }  
   */  
}  
```