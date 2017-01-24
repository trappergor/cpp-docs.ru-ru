---
title: "Ошибка компилятора C2472 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2472"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2472"
ms.assetid: 3b36bcdc-2ba5-4357-ab88-7545ba0551cd
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2472
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция" не может создаваться в управляемом коде "сообщение"; для генерации смешанного образа выполните компиляцию с параметром \/clr  
  
 Эта ошибка возникает при использовании типов, не поддерживаемых в управляемом коде, в чистой среде CLR. Для устранения этой ошибки выполните компиляцию с параметром **\/clr**.  
  
## Пример  
 Следующий пример приводит к возникновению ошибки C2472:  
  
```  
// C2472.cpp // compile with: /clr:pure // C2472 expected #include <cstdlib> int main() { int * __ptr32 p32; int * __ptr64 p64; p32 = (int * __ptr32)malloc(4); p64 = p32; }  
```  
  
## См. также  
 [\/clr \(компиляция CLR\)](../../build/reference/clr-common-language-runtime-compilation.md)