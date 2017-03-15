---
title: "Предупреждение компилятора (уровень 1) C4659 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4659"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4659"
ms.assetid: e29ba8db-7917-43f6-8e34-868b752279ae
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 1) C4659
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Директива \#pragma "pragma": при использовании зарезервированного сегмента "сегмент" поведение не определено; используйте \#pragma comment\(linker, ...\)  
  
 Параметр .drectve использовался для передачи параметра компоновщику.  Вместо этого для передачи параметра компоновщика рекомендуется использовать директиву pragma [comment](../../preprocessor/comment-c-cpp.md).  
  
```  
// C4659.cpp  
// compile with: /W1 /LD  
#pragma code_seg(".drectve")   // C4659  
```