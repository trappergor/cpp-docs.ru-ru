---
title: "Ошибка компилятора C2048 | Microsoft Docs"
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
  - "C2048"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2048"
ms.assetid: 44704726-85fc-42f0-afb9-194df8c4ca7c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Ошибка компилятора C2048
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

несколько вариантов, используемых по умолчанию  
  
 Оператор `switch` содержит несколько меток `default`. Удалите одну из меток `default` для устранения этой ошибки.  
  
 В следующем примере возникает ошибка C2048:  
  
```  
// C2048.cpp int main() { int a = 1; switch (a) { case 1: a = 0; default: a = 2; default:   // C2048 a = 3; } }  
```  
  
 Возможное решение:  
  
```  
// C2048b.cpp int main() { int a = 1; switch (a) { case 1: a = 0; default: a = 2; } }  
```