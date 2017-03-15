---
title: "Ошибка компилятора C2085 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2085"
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Ошибка компилятора C2085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор" : отсутствует в списке формальных параметров  
  
 Идентификатор был объявлен в определении функции, но не в списке формальных параметров \(только ANSI C\).  
  
 Следующий пример приводит к возникновению ошибки C2085:  
  
```  
// C2085.c  
void func1( void )  
int main( void ) {}   // C2085  
```  
  
 Возможный способ устранения данной ошибки:  
  
```  
// C2085b.c  
void func1( void );  
int main( void ) {}  
```  
  
 Без точки с запятой функция `func1()` выглядит как определение функции, а не как прототип, поэтому функция `main` определяется внутри `func1()`, что приводит к возникновению ошибки C2085 применительно к идентификатору `main`.