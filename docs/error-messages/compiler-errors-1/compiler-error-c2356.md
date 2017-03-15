---
title: "Ошибка компилятора C2356 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2356"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2356"
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Ошибка компилятора C2356
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

сегмент инициализации не должен изменяться в пределах записи преобразования  
  
 Возможные причины:  
  
-   Директиве `#pragma init_seg` предшествует код инициализации сегмента  
  
-   Директиве `#pragma init_seg` предшествует другая директива `#pragma init_seg`  
  
 Чтобы устранить эту ошибку, переместите код инициализации сегмента в начало модуля.  Если необходимо инициализировать несколько областей, переместите их в разные модули.  
  
 Следующий пример приводит к возникновению ошибки C2356:  
  
```  
// C2356.cpp  
#pragma warning(disable : 4075)  
  
int __cdecl myexit(void (__cdecl *)());  
int __cdecl myexit2(void (__cdecl *)());  
  
#pragma init_seg(".mine$m",myexit)  
#pragma init_seg(".mine$m",myexit2)   // C2356  
```