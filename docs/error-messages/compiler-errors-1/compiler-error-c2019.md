---
title: "Ошибка компилятора C2019 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2019"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2019"
ms.assetid: 4f37b1e1-9eca-418f-a4c3-141e8512d7b6
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2019
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ожидается директива препроцессора, найден 'character'  
  
 Символ следует за знаком `#`, но не является первым буквенным символом директивы препроцессора.  
  
 Следующий пример приводит к возникновению ошибки C2019:  
  
```  
// C2019.cpp  
#!define TRUE 1   // C2019  
```  
  
 Возможный способ устранения данной ошибки:  
  
```  
// C2019b.cpp  
// compile with: /c  
#define TRUE 1  
```