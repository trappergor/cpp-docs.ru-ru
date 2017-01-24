---
title: "Ошибка компилятора C3519 | Microsoft Docs"
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
  - "C3519"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3519"
ms.assetid: ca24b2bc-7e90-4448-ae84-3fedddf9bca7
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3519
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"недопустимый\_параметр" : недопустимый параметр атрибута embedded\_idl  
  
 Параметр, переданный атрибуту `embedded_idl` директивы [\#import](../Topic/%23import%20Directive%20\(C++\).md), не был распознан компилятором.  
  
 Для атрибута `embedded_idl` допустимы только параметры `emitidl` и `no_emitidl`.  
  
 Следующий пример приводит к возникновению ошибки C3519:  
  
```  
// C3519.cpp  
// compile with: /LD  
[module(name="MyLib2")];  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidcl")     
// C3519  
#import "C:\testdir\bin\importlib.tlb" embedded_idl("no_emitidl")     
// OK  
```