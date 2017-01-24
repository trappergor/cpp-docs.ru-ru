---
title: "Ошибка компилятора C2130 | Microsoft Docs"
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
  - "C2130"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2130"
ms.assetid: c6fd5a7e-8f28-4f67-99d1-95a13b0dff90
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2130
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В директиве \#line требуется строка, содержащая имя файла, вместо "токен"  
  
 Дополнительный токен имени файла после директивы [\#line](../Topic/%23line%20Directive%20\(C-C++\).md) `linenumber` должен быть строкой.  
  
 При компиляции следующего примера возникнет ошибка C2130:  
  
```  
// C2130.cpp int main() { #line 1000 test   // C2130 #line 1000 "test"   // OK }  
```