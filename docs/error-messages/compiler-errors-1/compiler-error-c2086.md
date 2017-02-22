---
title: "Ошибка компилятора C2086 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2086"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2086"
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Ошибка компилятора C2086
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"идентификатор": переопределение  
  
 Идентификатор определен несколько раз, или следующее объявление отличается от предыдущего.  
  
 Ошибка C2086 может возникать также из\-за увеличивающегося построения используемой сборки C\#.  Повторно соберите сборку C\#, чтобы устранить эту ошибку.  
  
 Следующий пример приводит к возникновению ошибки C2086:  
  
```  
// C2086.cpp  
main() {  
  int a;  
  int a;   // C2086 not an error in ANSI C  
}  
```