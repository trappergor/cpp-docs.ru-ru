---
title: "Ошибка компилятора C2191 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2191"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2191"
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2191
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

второй список параметров длиннее первого  
  
 Функция C была объявлена во второй раз с более длинным списком параметров.  Язык C не поддерживает перегруженные функции.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2191:  
  
```  
// C2191.c  
// compile with: /Za /c  
void func( int );  
void func( int, float );   // C2191 different parameter list  
void func2( int, float );   // OK  
```