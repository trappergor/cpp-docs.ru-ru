---
title: "Ошибка компилятора C2341 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2341"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2341"
ms.assetid: aa2a7da5-e1c8-4225-9939-5bdc50158f31
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ошибка компилятора C2341
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"имя\_раздела": до использования сегмент должен быть определен с помощью \#pragma data\_seg, code\_seg или section  
  
 Оператор [allocate](../Topic/allocate.md) указывает на сегмент, который еще не был определен с помощью директив pragma [code\_seg](../../preprocessor/code-seg.md), [data\_seg](../../preprocessor/data-seg.md) или [section](../../preprocessor/section.md).  
  
 Следующий пример приводит к возникновению ошибки C2341:  
  
```  
// C2341.cpp  
// compile with: /c  
__declspec(allocate(".test"))   // C2341  
int j = 1;  
```  
  
 Возможный способ устранения данной ошибки:  
  
```  
// C2341b.cpp  
// compile with: /c  
#pragma data_seg(".test")  
__declspec(allocate(".test"))  
int j = 1;  
```