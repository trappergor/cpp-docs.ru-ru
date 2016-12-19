---
title: "Ошибка компилятора C3011 | Microsoft Docs"
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
  - "C3011"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3011"
ms.assetid: 24c3a917-ebff-4deb-9155-23adf6468531
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C3011
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

не допускается встроенный код на языке ассемблера непосредственно внутри параллельной области  
  
 Параллельная область `omp` не может содержать инструкции встроенного кода на языке ассемблера.  
  
 В следующем примере возникает ошибка C3011:  
  
```  
// C3011.cpp // compile with: /openmp // processor: /x86 int main() { int   n = 0; #pragma omp parallel { _asm mov eax, n   // Delete this line to resolve this error. }   // C3011 }  
```