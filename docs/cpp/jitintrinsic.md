---
title: "jitintrinsic | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "jitintrinsic"
  - "jitintrinsic_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec - ключевое слово [C++], jitintrinsic"
  - "jitintrinsic __declspec - модификатор"
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# jitintrinsic
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Помечает функцию как значимую для 64\-разрядной среды CLR.  Этот модификатор используется с определенными функциями в библиотеках Microsoft.  
  
## Синтаксис  
  
```  
__declspec(jitintrinsic)  
```  
  
## Заметки  
 Ключевое слово `jitintrinsic` добавляет MODOPT \(<xref:System.Runtime.CompilerServices.IsJitIntrinsic>\) к сигнатуре функции.  
  
 Применять этот модификатор `__declspec` пользователям не рекомендуется, поскольку это может привести к непредсказуемым результатам.  
  
## См. также  
 [\_\_declspec](../cpp/declspec.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)