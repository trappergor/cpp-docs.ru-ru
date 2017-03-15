---
title: "auto_inline | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "auto_inline_CPP"
  - "vc-pragma.auto_inline"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_inline - прагма"
  - "прагмы, auto_inline"
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# auto_inline
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Исключает все функции, определенные в пределах диапазона со значением **off**, из числа кандидатов на автоматическое встроенное разворачивание.  
  
## Синтаксис  
  
```  
  
#pragma auto_inline( [{on | off}] )  
```  
  
## Заметки  
 Для использования директивы \#pragma **auto\_inline** поместите ее перед или сразу после определения функции \(но не внутри определения\).  Эта директива \#pragma начинает действовать с первого определения функции после вхождения данной директивы.  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)