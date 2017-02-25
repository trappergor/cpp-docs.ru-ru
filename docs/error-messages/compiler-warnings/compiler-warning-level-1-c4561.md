---
title: "Предупреждение компилятора (уровень 1) C4561 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4561"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4561"
ms.assetid: 3a10c12c-601b-4b6c-9861-331fd022e021
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Предупреждение компилятора (уровень 1) C4561
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

соглашение "\_\_fastcall" несовместимо с параметром "\/clr": переход на соглашение "\_\_stdcall"  
  
 Соглашение о вызове функций [\_\_fastcall](../../cpp/fastcall.md) не может использоваться с параметром компилятора [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  Компилятор игнорирует вызовы `__fastcall`.  Чтобы устранить это предупреждение, либо удалите вызовы к **\_\_fastcall**, либо не используйте при компиляции параметр **\/clr**.  
  
 Следующий пример приводит к возникновению ошибки C4561:  
  
```  
// C4561.cpp  
// compile with: /clr /W1 /c  
// processor: x86  
void __fastcall Func(void *p);   // C4561, remove __fastcall to resolve  
```