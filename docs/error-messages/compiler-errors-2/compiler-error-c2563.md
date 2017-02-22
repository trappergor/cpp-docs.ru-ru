---
title: "Ошибка компилятора C2563 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2563"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2563"
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C2563
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

несоответствие в списке формальных параметров  
  
 Список формальных параметров функции \(или указателя на функцию\) не соответствует параметрам другой функции \(или указателя на функцию\-член\).  В результате не удается выполнить назначение функций или указателей.  
  
 Следующий пример приводит к возникновению ошибки C2563:  
  
```  
// C2563.cpp  
void func( int );  
void func( int, int );  
int main() {  
   void *fp();  
   fp = func;   // C2563  
}  
```