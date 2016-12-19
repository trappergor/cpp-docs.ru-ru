---
title: "Ошибка компилятора C2480 | Microsoft Docs"
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
  - "C2480"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2480"
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2480
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"identifier": "thread" допускается только для статических элементов данных  
  
 Атрибут `thread` нельзя использовать с автоматической переменной, астатическим элементом данных, параметром функции, а также в объявлениях или определениях функции.  
  
 Атрибут `thread` используется только для глобальных переменных, статистических элементов данных и локальных статических переменных.  
  
 Следующий пример приводит к возникновению ошибки C2480:  
  
```  
// C2480.cpp  
// compile with: /c  
__declspec( thread ) void func();   // C2480  
__declspec( thread ) static int i;   // OK  
```