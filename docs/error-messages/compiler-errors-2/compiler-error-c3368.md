---
title: "Ошибка компилятора C3368 | Microsoft Docs"
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
  - "C3368"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3368"
ms.assetid: 5bfd5be4-dfa9-4b33-9612-010561b40955
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3368
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"объявление\_функции": недопустимое соглашение о вызове для IDL  
  
 В IDL\-файле можно использовать только соглашения о вызовах [\_\_stdcall](../../cpp/stdcall.md) или [\_\_cdecl](../Topic/__cdecl.md).  
  
 Следующий пример приводит к возникновению ошибки C3368:  
  
```  
// C3368.cpp // processor: x86 [idl_module(name="Name", dllname="Some.dll")]; [idl_module(name="Name")] int __fastcall f1();   // C3368  
```