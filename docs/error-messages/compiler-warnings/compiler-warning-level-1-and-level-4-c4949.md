---
title: "Предупреждение компилятора (уровень 1 и уровень 4) C4949 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4949"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4949"
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Предупреждение компилятора (уровень 1 и уровень 4) C4949
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

директивы pragma "managed" и "unmanaged" имеют смысл только при компиляции с параметром "\/clr\[:параметр\]"  
  
 Компилятор пропускает директивы pragma [managed](../../preprocessor/managed-unmanaged.md) и unmanaged, если исходный код компилируется без использования параметра [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  Это предупреждение является информационным.  
  
 Следующий пример приводит к возникновению ошибки C4949:  
  
```  
// C4949.cpp  
// compile with: /LD /W1  
#pragma managed   // C4949  
```  
  
 Если директива **\#pragma unmanaged** используется без параметра **\/clr**, C4949 является предупреждением 4 уровня.  
  
 Следующий пример приводит к возникновению ошибки C4949:  
  
```  
// C4949b.cpp  
// compile with: /LD /W4  
#pragma unmanaged   // C4949  
```