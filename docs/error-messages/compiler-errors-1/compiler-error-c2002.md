---
title: "Ошибка компилятора C2002 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2002"
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C2002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимая многобайтовая знаковая константа  
  
 Многобайтовая знаковая константа недопустима.  
  
### Чтобы устранить ошибку, следует проверить следующие возможные причины ее возникновения.  
  
1.  Многобайтовая знаковая константа содержит больше байт, чем предполагалось.  
  
2.  Не включен стандартный заголовок STDDEF.h.  
  
3.  Многобайтовые знаки нельзя объединять с обычными строковыми литералами.  
  
4.  Многобайтовая знаковая константа должна начинаться со знака "L".  
  
    ```  
    L'mbconst'  
    ```  
  
5.  В Microsoft C\+\+ текстовые аргументы препроцессора должны быть представлены символами ASCII.  Например, директива `#pragma message(L"string")` недопустима.