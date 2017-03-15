---
title: "Ошибка компилятора C2128 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "c2128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2128"
ms.assetid: 08cbf734-75b3-49f2-9026-9b319947612d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C2128
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"функция" : директива pragma alloc\_text\/same\_seg применима только к функциям с компоновкой C  
  
 Директива `pragma` `alloc_text` может использоваться только с функциями, для которых объявлена компоновка C.  
  
 Следующий пример приводит к возникновению ошибки C2128:  
  
```  
// C2128.cpp  
// compile with: /c  
  
// Delete the following line to resolve.  
void func();  
// #pragma alloc_text("my segment", func)   // C2128  
  
extern "C" {  
void func();  
}  
  
#pragma alloc_text("my segment", func)  
void func() {}  
```