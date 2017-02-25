---
title: "Ошибка компилятора C2006 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2006"
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

в "директиве", вместо имени файла обнаружена "лексема"  
  
 В таких директивах, как [\#include](../../preprocessor/hash-include-directive-c-cpp.md) или [\#import](../Topic/%23import%20Directive%20\(C++\).md), должно использоваться имя файла.  Чтобы исправить эту ошибку, следует убедиться, что *лексема* является допустимым именем файла.  Также следует заключить имя файла в двойные кавычки или угловые скобки.  
  
 Следующий пример приводит к возникновению ошибки C2006:  
  
```  
// C2006.cpp  
#include stdio.h   // C2006  
```  
  
 Возможный способ устранения данной ошибки:  
  
```  
// C2006b.cpp  
// compile with: /c  
#include <stdio.h>  
```