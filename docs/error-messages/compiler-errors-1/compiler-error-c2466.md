---
title: "Ошибка компилятора C2466 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2466"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2466"
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2466
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

невозможно выделить память для массива постоянного нулевого размера  
  
 Выделен или объявлен массив нулевого размера.  Размер массива должен определяться константным выражением, имеющим целое значение больше нуля.  Объявление массива с нулевым индексом допускается только для членов класса, структуры или объединения и только в расширениях Microsoft \(см. описание параметра [\/Ze](../../build/reference/za-ze-disable-language-extensions.md)\).  
  
 Следующий пример приводит к возникновению ошибки C2466:  
  
```  
// C2466.cpp  
// compile with: /c  
int i[0];   // C2466  
int j[1];   // OK  
char *p;  
```