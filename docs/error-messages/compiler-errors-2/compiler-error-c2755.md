---
title: "Ошибка компилятора C2755 | Microsoft Docs"
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
  - "C2755"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2755"
ms.assetid: 8ee4eeb6-4757-4efe-9100-38ff4a96f1de
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2755
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"параметр": параметр частичной специализации, не являющийся типом, должен быть простым идентификатором  
  
 Не являющийся типом параметр должен быть простым идентификатором, который во время компиляции может сопоставляться одному идентификатору или константному значению.  
  
 Следующий пример приводит к возникновению ошибки C2755:  
  
```  
// C2755.cpp  
template<int I, int J>  
struct A {};  
  
template<int I>   
struct A<I,I*5> {};   // C2755  
// try the following line instead  
// struct A<I,5> {};  
```