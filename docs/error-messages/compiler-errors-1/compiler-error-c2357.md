---
title: "Ошибка компилятора C2357 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2357"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2357"
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2357
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": должна быть функцией типа "тип"  
  
 В коде объявляется версия функции `atexit`, которая не соответствует версии, объявленной компилятором на внутреннем уровне.  Объявите функцию `atexit` как:  
  
```  
int __cdecl atexit(void (__cdecl *)());  
```  
  
 Дополнительные сведения см. в разделе [init\_seg](../../preprocessor/init-seg.md).  
  
 Следующий пример приводит к возникновению ошибки C2357:  
  
```  
// C2357.cpp  
// compile with: /c  
// C2357 expected  
#pragma warning(disable : 4075)  
// Uncomment the following line to resolve.  
// int __cdecl myexit(void (__cdecl *)());  
#pragma init_seg(".mine$m",myexit)  
```