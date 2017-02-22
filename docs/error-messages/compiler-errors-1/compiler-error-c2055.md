---
title: "Ошибка компилятора C2055 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2055"
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

требуется список формальных параметров, а не список типов  
  
 Определение функции содержит список типов параметра, а не список формальных параметров.  Стандарт ANSI языка C требует присвоения имен формальным параметрам, если только они не являются пустыми или многоточием \(`...`\).  
  
 Следующий пример приводит к возникновению ошибки C2055:  
  
```  
// C2055.c  
// compile with: /c  
void func(int, char) {}  // C2055  
void func (int i, char c) {}   // OK  
```