---
title: "Предупреждение компилятора (уровень 1) C4090 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4090"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4090"
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 1) C4090
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

операция: разные квалификаторы "модификатор"  
  
 Переменная, использующаяся в операциях, определена при помощи указанного модификатора, не разрешающего изменять ее без ведома компилятора.  Выражение скомпилировано без модификаций.  
  
 Это предупреждение может появляться, когда указатель на элемент **const** или `volatile` присваивается указателю, не объявленному как указатель на **const** или `volatile`.  
  
 Это предупреждение не выдается для программ, написанных на языке C.  В программах, написанных на C\+\+, компилятор выдает ошибку [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md).  
  
 Следующий пример приводит к возникновению ошибки C4090:  
  
```  
// C4090.c  
// compile with: /W1  
int *volatile *p;  
int *const *q;  
int **r;  
  
int main() {  
   p = q;   // C4090  
   p = r;  
   q = p;   // C4090  
   q = r;  
   r = p;   // C4090  
   r = q;   // C4090  
}  
```