---
title: "Неустранимая ошибка C1017 | Microsoft Docs"
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
  - "C1017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1017"
ms.assetid: 5542e604-599d-4e36-8f83-1d454c5753c9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Неустранимая ошибка C1017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

недопустимое константное выражение целого типа  
  
 Выражение в директиве `#if` не существовало, либо не являлось константным.  
  
 Константы, определенные с помощью `#define`,  должны иметь значения, которые при использовании в директиве `#if`, `#elif` или `#else` являются константными значениями целого типа.  
  
 Следующий пример приводит к возникновению ошибки C1017:  
  
```  
// C1017.cpp  
#define CONSTANT_NAME "YES"  
#if CONSTANT_NAME   // C1017  
#endif  
```  
  
 Возможный способ устранения данной ошибки:  
  
```  
// C1017b.cpp  
// compile with: /c  
#define CONSTANT_NAME 1  
#if CONSTANT_NAME  
#endif  
```  
  
 Поскольку `CONSTANT_NAME` является строкой, а не целым числом, директива `#if` выдает неустранимую ошибку C1017.  
  
 В иных случаях препроцессор оценивает незаданную константу как ноль.  Это может привести к нежелательным результатам, как показано в следующем примере.  Константа `YES` не задана, поэтому оценивается как ноль.  Выражение `#if` `CONSTANT_NAME` является ложным, и код, используемый в `YES`, удаляется препроцессором.  Константа `NO` также не задана \(ноль\), поэтому директива `#elif` `CONSTANT_NAME==NO` является истинной \(`0 == 0`\), вследствие чего препроцессор оставляет код в части `#elif` оператора, что противоречит запланированному поведению.  
  
```  
// C1017c.cpp  
// compile with: /c  
#define CONSTANT_NAME YES  
#if CONSTANT_NAME  
   // Code to use on YES...  
#elif CONSTANT_NAME==NO  
   // Code to use on NO...  
#endif  
```  
  
 Чтобы увидеть, каким образом компилятор обрабатывает директивы препроцессора, следует использовать [\/P](../../build/reference/p-preprocess-to-a-file.md), [\/E](../../build/reference/e-preprocess-to-stdout.md), или [\/EP](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md).