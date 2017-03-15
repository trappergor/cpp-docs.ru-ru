---
title: "Предупреждение компилятора (уровень 1) C4227 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4227"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4227"
ms.assetid: 78f98374-c00b-4000-aefa-1b1c67b4666b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Предупреждение компилятора (уровень 1) C4227
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

устаревший элемент: пропуск квалификаторов для ссылки  
  
 Использование квалификаторов, например `const` или `volatile` для ссылок C\+\+ более не рекомендуется.  
  
## Пример  
  
```  
// C4227.cpp  
// compile with: /W1 /c  
int j = 0;  
int &const i = j;   // C4227  
```