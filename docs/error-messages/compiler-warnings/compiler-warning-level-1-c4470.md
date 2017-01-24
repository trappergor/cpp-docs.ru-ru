---
title: "Предупреждение компилятора (уровень 1) C4470 | Microsoft Docs"
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
  - "C4470"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4470"
ms.assetid: f52a3eaa-a235-4747-a47d-9ec4ad4cb0ea
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Предупреждение компилятора (уровень 1) C4470
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

при использовании параметра \/clr директивы pragma контроля плавающей точки игнорируются  
  
 Директивы pragma элементов управления с плавающей запятой  
  
-   [fenv\_access](../../preprocessor/fenv-access.md)  
  
-   [float\_control](../Topic/float_control.md)  
  
-   [fp\_contract](../../preprocessor/fp-contract.md)  
  
 игнорируются при использовании параметра [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  
  
 Следующий пример приводит к возникновению ошибки C4470:  
  
```  
// C4470.cpp  
// compile with: /clr /W1 /LD  
#pragma float_control(except, on)   // C4470  
```